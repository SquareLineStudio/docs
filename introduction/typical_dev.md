# Typical development workflow

## Create a New Project

The first step is to create a new SquareLine Studio project. For further information, please check [**Getting Started**](/docs/introduction/getting_started) section. At this moment you can create only a simulator project.  Using the simulator project, you can create a platform independent application. (In the later versions various development boards will be supported.) You have nothing to do but

- give a name to your project
- select its location
- choose the resolution, color depth and a theme you prefer 

By doing this, a new blank screen will be created automatically. Besides a new folder for the project will be added to the selected location containing some project files and an `Assets` folder.

## Create and Organize Screen Content

Images, created in Photoshop or any other designer software, should be copied into the `Assets` folder of the project. Fonts, needed by the project, should be placed into the `Asset/Font` folder. These images and fonts will be appeared in the [**Assets Panel**](/docs/dev_env/assetes).

## Create Widgets and Events on the Screen

You can find widgets (e.g. button, label, image, etc.) in the [**Widgets Panel**](/docs/dev_env/widget). To add these widgets to the screen you should click on the icon of the widget or simply drag it onto the screen. If a widget is selected, you can add events to it at the bottom of the [**Inspector Panel**](/docs/dev_env/inspector) to create interactions or play an animation.

## Simulate and Export Your Project

Uniquely, you can test your working project directly in the SquareLine Studio in a blink of an eye. Using the `Play` button in the top-right hand corner of the [**Screen area view**](/docs/layout#editable-view), you can start the simulation of your project. In "Play mode", you have the opportunity to refine the settings of the widgets, including the parameters of styles and animations connected to them.

## Export a project

In the current version you can export ready to use simulator project for C/C++ and MicroPython languages. In `File/Projet Settings` you can set the target language and IDE/SDK. You can select either MicroPython with MakeFile project or C/C++ with Eclipse project. In this window you can also change the resolution and color depth of the display. 

After that, by clicking the `Export/Export Project` menu you can browse where to export the project. By selecting a location project will be there in a few seconds.

The exported project doesn't contain the UI itself. Typically the project is exported only once (or a few times) and later only the UI files are updated in it. It ensures that your modifications in other parts of the project are not overwritten. 

### Project Information File

When saving a project, a project.info file is generated alongside the project file in the project directory. This file contains metadata related to the last save, such as the timestamp, project version, and other relevant details. The project.info file is also included in the exported project, making it easy to identify and verify the version of both the saved and exported project.

### Export Path Configuration File

A .slp file is created in the project directory to store export path configurations. This file saves the export paths selected during the export process, allowing multiple users to share the same project without needing to reconfigure export paths each time. The .slp file ensures consistent export destinations across different sessions and users.

## Export UI files

To actual UI files can be exported from the `Export/Export Files` menu. It will also ask for a location for the files. This location is saved and if you export files later this path will be used. (It can be modified in the `File/Project Setting/Export Path` field.)

The exported projects contain a "README" file which tells which is preferred location for the UI files inside the project. 

The UI files also can be exported without having a project exported by SquareLine Studio. It means if you have prepared a project (e.g. for an embedded system) you can export the UI files there too. In this case, you need to write the drivers and take care of building the files. 

In case of C/C++ the following folder created:

- `screens` folder which contains the the C files for each screen
- `images` folder which contains the images converted to C files
- `fonts` folder which contains the fonts converted to C files
- `components` folder which contains the C files for each component. 

These special files will be created as well:

- `ui.c` the main file of the UI which initializes the screen, components, styles, animations, etc
- `ui.h` you need to include this the see the widgets and functions
- `ui_helper.c` and `ui_helper.c` used by `ui.c` internally
- `ui_events.c` skeletons for functions used as "Call function" event. You can add the implementation of the functions here.
- `components/ui_comp_hook.c` you can add custom code which will be called at the end of the component creation to customize the given components
- `CMakeList.txt` can be used in CMake build system to add the ui folder. Just add `add_subdirectory(ui)` to the parent `CMakeList.txt` file
- `filelist.txt` the list of C files separated by `\n`. Can be used by any build system if needed.

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

> The new versions (min. 1.3.0) of SquareLine Studio export the Arduino UI projects as an Arduino library.
> 
> If you would like to export only the UI files into a custom Arduino project, you need to add this folder this folders to your library folder and export the UI files into the src folder.
> 
> "this folder" link: https://github.com/SquareLineStudio/board_arduino_tft_espi/tree/v1.1.0/__ui_project_name__/libraries/ui

## UI Destruction Functions

Starting from version 1.5.2, SquareLine Studio has introduced several important enhancements to the project structure and memory management capabilities that make your UI development more modular and efficient.

### Improved Screen File Organization

Screens are now exported into separate files, with each screen getting its own header file. These files contain declarations for all object variables located on that particular screen, making it easier to manage and locate screen-specific elements.

### Screen Destruction Functions

Each screen now comes with a dedicated `screen_destroy()` function, allowing you to:

- Free resources associated with screen objects
- Reset all related variables to NULL
- Properly clean up memory when transitioning between screens

This is particularly useful for memory-constrained embedded systems where resource management is critical.

### Screen-specific Events

All event functions and their declarations related to a specific screen have been moved to that screen's C/H files. This reorganization provides several benefits:

- The main `ui.c` and `ui.h` files are now much cleaner and more concise
- Finding screen-specific variables and event handlers is more intuitive
- Code maintenance becomes simpler with better separation of concerns

### Global UI Destruction Function

A new global `ui_destroy()` function has been added to `ui.c`. This function:

- Destroys all screens at once
- Completely releases all UI resources
- Allows for complete UI rebuilding

This is especially valuable for applications requiring localization or dynamic UI reconstruction, as it enables you to rebuild the entire UI with different language settings without memory leaks.

### Usage Example

```c
// To destroy a specific screen
ui_Screen1_destroy();

// To destroy the entire UI (all screens)
ui_destroy();

// Example of rebuilding UI after language change
void change_language(int language_id) {
    // Destroy current UI
    ui_destroy();

    // Set new language
    set_current_language(language_id);

    // Rebuild UI with new language
    ui_init();
}
```

## UI Re-localization Functions

Starting from version 1.5.3, SquareLine Studio has introduced powerful re-localization capabilities that complement the destruction functions and provide efficient language switching for multi-language applications.

### Global UI Re-localization Function

A new global `ui_relocalize()` function has been added to `ui.c`, available when multi-language support is enabled in your project. This function provides an efficient way to update all text labels throughout your UI without the overhead of recreating the entire interface.

#### Key Features and Benefits

The `ui_relocalize()` function offers several advantages over traditional UI rebuilding approaches:

- **Resource Efficiency**: Updates existing UI elements in place using LVGL's `_()` localization function without destroying and recreating screens
- **Performance Optimization**: Significantly faster than the destroy-rebuild cycle, making it ideal for real-time language switching
- **Memory Conservation**: Avoids memory fragmentation and temporary allocation spikes associated with UI reconstruction
- **Preserved State**: Maintains current UI state, animations, and user interactions during language changes

#### Screen-specific Re-localization

Each screen also gets its own dedicated `<screen_name>_screen_relocalize()` function, allowing you to:

- Update text labels on specific screens only
- Perform targeted localization updates for better performance
- Maintain granular control over which parts of your UI get updated

#### Usage Scenarios

This functionality is particularly valuable for:

- Applications requiring frequent language switching
- Memory-constrained embedded systems where UI rebuilding is costly
- Real-time applications where UI responsiveness is critical
- Systems with complex UI states that shouldn't be disrupted during localization

#### Usage Example

```c
// To re-localize a specific screen
ui_Screen1_relocalize();

// To re-localize the entire UI (all text labels)
ui_relocalize();

// Example: Efficient language change without UI rebuilding
void change_language(int language_id) {
    // Set new language
    set_current_language(language_id);

    // Re-localize UI with the new language
    ui_relocalize();
}
```
