# Typical development workflow

## Create a New Project

The first step is to create a new SquareLine Studio project. For further information, please check [**Getting Started**](https://docs.squareline.io/docs/introduction/getting_started) section. At this moment you can create only a simulator project.  Using the simulator project, you can create a platform independent application. (In the later versions various development boards will be supported.) You have nothing to do but

- give a name to your project
- select its location
- choose the resolution, color depth and a theme you prefer 

By doing this, a new blank screen will be created automatically. Besides a new folder for the project will be added to the selected location containing some project files and an `Assets` folder.

## Create and Organize Screen Content

Images, created in Photoshop or any other designer software, should be copied into the `Assets` folder of the project. Fonts, needed by the project, should be placed into the `Asset/Font` folder. These images and fonts will be appeared in the [**Assets Panel**](https://docs.squareline.io/docs/dev_env/assetes).

## Create Widgets and Events on the Screen

You can find widgets (e.g. button, label, image, etc.) in the [**Widgets Panel**](https://docs.squareline.io/docs/dev_env/widgets). To add these widgets to the screen you should click on the icon of the widget or simply drag it onto the screen. If a widget is selected, you can add events to it at the bottom of the [**Inspector Panel**](https://docs.squareline.io/docs/dev_env/inspector) to create interactions or play an animation.

## Simulate and Export Your Project

Uniquely, you can test your working project directly in the SquareLine Studio in a blink of an eye. Using the `Play` button in the top-right hand corner of the [**Screen area view**](https://docs.squareline.io/docs/layout#editable-view), you can start the simulation of your project. In "Play mode", you have the opportunity to refine the settings of the widgets, including the parameters of styles and animations connected to them.

## Export a project

In the current version you can export ready to use simulator project for C/C++ and MicroPython languages. In `File/Projet Settings` you can set the target language and IDE/SDK. You can select either MicroPython with MakeFile project or C/C++ with Eclipse project. In this window you can also change the resolution and color depth of the display. 

After that, by clicking the `Export/Export Project` menu you can browse where to export the project. By selecting a location project will be there in a few seconds.

The exported project doesn't contain the UI itself. Typically the project is exported only once (or a few times) and later only the UI files are updated in it. It ensures that your modifications in other parts of the project are not overwritten. 

## Export UI files

To actual UI files can be exported from the `Export/Export Files` menu. It will also ask for a location for the files. This location is saved and if you export files later this path will be used. (It can be modified in the `File/Project Setting/Export Path` field.)

The exported projects contain a "README" file which tells which is preferred location for the UI files inside the project. 

The UI files also can be exported without having a project exported by SquareLine Studio. It means if you have prepared a project (e.g. for an embedded system) you can export the UI files there too. In this case, you need to write the drivers and take care of building the files. 

In case of C/C++ the following files will be created

- `ui.c` the UI code itself
- `ui.h` you need to include this the see the widgets and functions
- `ui_helper.c` and `ui_helper.c` used by `ui.c` internally
- `ui_img_*.c` the converted images
- `ui_fonts_*.c` the converted fonts
- `ui_events.c` skeletons for functions used as "Call function" event. You can add the implementation of the functions here.

To set up a C/C++ UI

1. Include `ui.h`
2. Call `lv_init();`
3. Set up the display and input device drivers
4. Call `ui_init();`

For MicroPython these files are created

- `ui.py` the UI code itself
- `ui_helper.py` used by `ui.py` internally
- `ui_images.py` all the the converted images
- `ui_font_*.bin` the converted fonts
- `ui_events.py` skeletons for functions used as "Call function" event. You can add the implementation of the functions here.

To set up a MicroPython UI

- `import lvgl` and initialize it by `lv.init()`
- Set up the display and input device drivers
- `import ui` 
