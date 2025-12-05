---
title: Changelog
---

## # Version 1.5.4

Release date: 9 October 2025

### New features

- Added Coffee Machine example program
- New out animation phases for screen transitions
- Project.info file saved alongside project file, containing last save details; included in export for version identification
- .slp file added alongside project file, storing export paths to simplify multi-user workflows

### Bugfixes

- Fixed export of all UI files when no board template path is set, ensuring assets are included
- Fixed underline issue in Enter Passcode
- Fixed pointer self-assignment issue
- Fixed Slider animation time style not working
- Fixed incorrect code in SLS export helpers.c for _ui_screen_delete: updated to...

## Version 1.5.3

Release date: 3 June 2025

### New features

- UI Re-localization Functions

### Bugfixes

- Fixed flat export error
- Fixed dynamic watchdog issue 

## Version 1.5.2

Release date: 13 May 2025

### New features

- Added UI destroy functions
- Theme optimization
- New event trigger: LV_EVENT_INSERT
- Option to export in pre-1.5.1 format

### Bugfixes

- Fixed font naming issue with hyphens
- Fixed toast message disappearing in Play mode during LVGL crash
- Fixed issue with creating fonts with identical names
- Loading optimization for large projects
- Image Button default size set to 64x64
- Fixed full screen mode persistence when launching previous versions
- Fixed KS_Diagnostics startup issue on Linux versions
- Roller widget default height set to 100px
- Fixed rendering order of non-component items within components

## Version 1.5.1

Release date: 03 March 2025

### New features

- Added LVGL 9.2.2 support
- [Screen Group](/docs/dev_env/screens#add-screen-and-screen-group) Implemented Screen Groups functionality
- [Snappable Scroll](/docs/dev_env/inspector#scrolling)  Added new snappable scroll functions
- Added warning dialog when deleting widgets or components with custom aliases
- Widget state is now displayed in the Error list
- Added warning dialog during export when assets or components are missing
- Updated OBP files for:
  - arduino_tft_espi
  - cmake_sdl
  - micropython
  - sim_sdl_eclipse
  - stm32h7b3i
  - visual_studio
  - vs_code_sdl
- Added new board files for:
  - Elecrow DIS01135P
  - Elecrow DIS09024P
  - Renesas RA6M3 HMI
  - Nuvoton NuMaker HMI M467
  - Nuvoton NuMaker HMI M55M1

### Bugfixes

- Fixed custom aliases not being duplicated when duplicating widgets and components
- Fixed error panel content disappearing when deleting widgets
- Fixed application freezing when font names contain hyphens
- Fixed images and background image style images being exported when "don't export" option is enabled
- Fixed binary PNG export not working when path is configured in project settings
- Removed excessive line spacing in exported code
- Fixed event components still being exported when parent widget/component has "don't export" enabled
- Fixed case sensitivity issues in object naming
- Fixed application freezing after undoing screen deletion

## Version 1.5.0

Release date: 29 October 2024

### New features

- Added padding style to Roller widget.
- Implemented "Don't export" functionality for widgets.
- [Custom variable alias](/docs/dev_env/inspector#custom-variable-alias) - support for widgets with unique prefixes.
- Separated translation checkbox from text properties in components.
- Added template image export option in project settings.
- Added "Start maximized window" checkbox in preferences.
- Optimized project file by excluding default States and Flags from saving.
- New object naming option: (Widget_Screen)_Name.
- Improved theme handling performance in exported projects.
- Added "Show log file" option in File menu to display the latest application log.

### Bugfixes

- Fixed widget ID changes during project export.
- Resolved error message display issues during name input.
- Fixed component element name modification export issue with purple checkmark.
- Fixed event main class changing to container during save.
- Resolved compilation errors in Ui_temporary_image.cpp.
- Fixed event window behavior when events are collapsed.
- Corrected widget selection issue after deletion on screen.
- Fixed popup window movement affecting underlying widgets.
- Resolved widget bounding box rotation issues with transform style.
- Performance optimization and speed improvements.
- Handled infinite loops in MicroPython.
- Improved runtime error handling in MicroPython.
- Fixed Bg Image override within components in LVGL 9.1.
- Fixed drawing issue when images of an imageset are deleted after set in an animation.
- Various minor fixes.

## Version 1.4.2

Release date: 03 August 2024

### New features

- Transform style: Now every widget can have min and max width and height, as well as be rotated and scaled.
- Optimization of error handling, detailed error messages appear in the console in case of issues.
- Event filter icon in the hierarchy.
- A toast message appears in the launcher with information related to board downlodas.
- If multiple widgets are stacked on top of each other, clicking multiple times in the same spot will select the other widget.
- Case-insensitive search in the hierarchy search.
- The auto-save function overwrites the project file as well, not just creating a copy.
- Speeding up operations performed with components.
- The minimum height of panels can be set smaller.
- The scroll bar in the editor section has been increased, making it easier to use.

### Bugfixes

- On MacOS and Linux, screens can now be switched by clicking within the screen, not just on the screen header.
- Fixed the display speed of the event action dropdown list for many widgets.
- Fixed a crash when writing an excessively large number for outline width.
- Fixed the problem of changing the layout in the case of the component.
- Exception handling for syntax errors.
- Fixed an issue where the default value in the Switch theme event would appear as an error.
- Fixed a crash when an unknown format file is placed in the assets folder.
- Fixed the shape parameter to change when switching boards.
- Fixed an issue where an error panel appears if the keyboard target is not specified within a component.
- Handling of assets with the same name.
- Fixed a crash when undoing a detach component action.
- Fixed the text alignment option in the text area widget.
- Fixed a crash if there are special characters in the project path.
- Fixed the Animation imgset const mismatch warning at build.

## Version 1.4.1

Release date: 28 May 2024

### New features

- Support for LVGL 9.1
- New stable undo engine
- An indicator on the hierarchy panel shows when an event is added
- Error handling tab panel displaying items without selected targets
- Image inner align in LVGL 9.1
- Image stretch function
- Maximum project resolution increased to 4096
- Toast message for creating and modifying scalar fonts
- Ability to specify if a board is rectangular or circular in the Open Board Platform (.slb) file
- New state: Edited state
- Text in the console panel can be selected and copied
- Tab panel height can be resized smaller
- New board files and fixes

### Bugfixes

- Board loading problems on the launcher screen
- Fixed dropdown widget border style issue
- Fixed TextArea alignment issue
- Improved speed of the EV charger demo
- Fixed options checkbox in roller components changing enters to '\n' when toggled
- Corrected screen positioning when switching resolutions
- Fixed animation naming issue
- Increased editable screens speed on MacOS with LVGL 8.3.11
- Fixed lack of notification for unsaved changes when exiting with undo history OFF
- Fixed screen positioning not updating after changing resolution in project settings

### BSP Boards Changes

#### New Boards

- CMake (includes VScode and Eclipse project settings for debugging and scripting)
- Visual Studio 2022

#### Improved

- VScode (better config, added lv_drivers, new LVGL9 version)
- Eclipse (better build configs, LVGL9 version)
- Visual Studio (minor corrections, better alpha=0 image refreshing, resizability with LVGL9)
- MicroPython (pre-built executables, build scripts/source code fixes, LVGL9 version)
- Arduino-TFT_eSPI (updated TFT_eSPI driver, added driver comparison tables for Pico in README)
- Raspberry Pi (max resolution 4096, configs, LVGL9 version)
- evkmimxrt595 (circle default in .slb file)

## Version 1.4.0

Release date: 01 Marc 2024

### New features

- Screens are freely movable on the editor's editable view
- Management of global colors and themes
- Theme switch action
- Support of LVGL 8.3.11
- Handling assets on external drives
- Exporting assets in compressed format
- Option for prefix widget names
- Clickable flag is disabled by default in container widgets
- Components cannot be deleted while they are in the project
- Command-line export without launching SquareLine Studio
- New example projects in multiple resolutions: EV charger, E-bike
- Widgets can also be inserted into empty screens from the clipboard

### Bugfixes

- If I delete a component from the project, it also removes it from the previously exported code.
- Fixed of compile error, in case of a custom font, if a component is is not in use in the screen.
- Fixed the Textarea component keyboard switch error.
- Ability to drag widgets from the widget panel into the hierarchy.
- Accelerated saving and loading.
- Compile error on macOS: "The name 'format_options' does not exist in the current context."
- Fontconverter works on ARM Mac systems without Rosetta.
- If formatting SPJ is enabled in preferences, it also formats the SLL file.
- Fixed 'math.h missing' error caused by Spinbox.
- Fixed the chart widget freezing when no value is specified in the data section.
- Fixed wrong default value for the Arc widget.
- Fixed the program freezing when the textarea widget is edited within a component.

## Version 1.3.4

Release date: 11 December 2023

### New features

- Pan around the screen by moving the area around the screens.
- Select the default element to be displayed in the Roller widget.
- Delete assets from the assets panel.
- UI reset function in the 'Preferences' menu.
- Padding style added to Checkbox bullet style.
- Text style added to the main part of the Spinbox widget.
- Copy-Paste functionality in the hierarchy panel.
- Examples support multiple resolutions.
- Icons of dragged widgets from the widget panel are visible under the mouse cursor.
- Special characters in the project name are changed to '_' in the exported code.
- You cannot delete a component if it has been created in the project

### Bugfixes

- Fix for incorrect export in the case of palettized PNG.
- Formatting fix for exported code.
- Fix for screen jump when moving a widget on the hierarchy panel.
- Fix for the unlock function in the hierarchy panel.
- Dropdown widget export fix for the 'list align left' option.
- Overflow of uievent.c from CMakeLists.txt in UI export.
- Bar widget range and symmetrical settings not exported.
- Play mode stops when opening the launcher.
- 'Label property' action in events exported as 'to be translated'.
- Fix for the generation of unused variables.
- Ability to set a relative path for export paths in project settings.
- Renamed screens are now deleted during export.
- Fix for license check error messages.
- Editing duplicate components with the same name as the original component is now possible.
- Manufacturer list breaks into multiple rows in the launcher create menu.
- Override of ui_comp_hook.c in every export fixed.
- Flax layout export fixed for component modifications.
- Call function action not generated for certain components, now fixed.
- Fix for when saving a component, the images in the component change to the default image.
- Fix for call function action not being exported from certain components.

## Version 1.3.3

Release date: 6 November 2023

### New features

- Increase in the Personal License limitation: Now allows a maximum of 10 screens (previously 5) and a maximum of 150 widgets (previously 50)
- Improved performance during widget creation, selection, hierarchy rearrangement, and inspector property modifications
- Floating license support
- Optimization of SPJ file
- Optimization of component files (To optimize your existing components, press the "Edit Component" and then "Save Component" buttons in the inspector panel)
- Introduction of a new Screen panel (Screens and hierarchy elements are now in separate panels)

### Bugfixes

- Added support for M1/M2 MacOS ARM CPUs
- Fixed a Spinbox export issue related to the main style
- Dropdown widget focused state fixed
- Improved code formatting
- Fixed an issue with "Don't export screen."
- Fixed a flex export issue
- Corrected the missing prefix in the Screen .c file

## Version 1.3.2

Release date: 30 August 2023

### New features

- General speed up
- Add a "Don't export screen" proty to screens
- Flat export (for better Arduino compatibility)
- Allow 128 character long widget names
- Add NXP and ST boards

### Bugfixes

- Make components events run
- Fix any issue when overwriting styles properties in components
- Fix Background style usage of Spinbox
- Fix the history panel
- Fix the Object naming option in Project preferences
- Fix incorrectly setting the default font lv_conf.h
- Fix ui_Screen is not defined (Python link error)

## Version 1.3.1

Release date: 13 July 2023

### New features

- Faster project load and save
- Faster component creation and modification
- Speed up SLS in general
- Enable Auto save by default
- Add Tabview widget
- Add Spinbox widget
- Set UI scale to 150% by default on high DPI monitors
- Add new states for styles:  FOCUS_KEY, CHECKED | FOCUSED, CHECKED | FOCUS_KEY
- New event triggers: KEY,  LV_EVENT_SHORT_CLICKED
- New event actions: delete screen, step spinbox
- Improve Undo
- Add Temporary screen options (If enabled on a screen, that screen will automatically created on when loaded, and deleted when unloaded)
- Add new Nuvoton board
- Add new flags:  SCROLL_WITH_ARROW, OVERFLOW_VISIBLE
- Add "Fit to screen" icon to the header

### Bugfixes

- Do not overwrite ui_comp_hook.c on export
- Fix calendar export issue
- Save Flex layout paddings
- Add function in ui_events.h only once

## Version 1.3.0

Release date: 3 May 2023

### New features

- Option to set the default ALIGN in Project preferences- Organize the exported code into folders
- Show the current cursor position on the header
- Export CMakeFile.txt, mk and a general filelist for easier integration
- Option to send crash logs
- Add LVGL 8.3.6
- Add lv_indev_wait_release to gesture events
- Saving the chart series data into components
- Organize the exported C code into folders
- [Multi language support](/docs/multilanguage)

### Bugfixes

- Fix error with chart export 
- Fix color picker on Linux

> **Important**
> 
> **Due the new exported project structure at least the the v1.1.0 version of the Arduino project needs to be used from SLS v1.3.0.**

## Version 1.2.3

Release date: 29 Mar 2023

### New features

- Use multiple cores during exporting
- Add popup if some information are missing in the font converter
- Color style properties can be set with a single hex number
- Update the colors real time while the colors are adjusted in the color picker
- Add popup in case of  the portable license if you are logged in from another computer too 
- Enable the build in montserrat fonts automatically if needed

### Bugfixes

- Fix the project not loading due to issues with the images
- Fix exporting the images in the correct color depth in MicroPython
- Do not export the images deleted from the assets folder
- Fix mixing the order of screen during loading the projects 
- Update the color if the hex value has been changed in the color picker
- Fix the size of the color picker on Linux

## Version 1.2.2

Release date: 20 Mar 2023

### New features

- Use multiple cores during exporting
- Include ui_comp.h in ui.h
- Add a hook for component creation
- Initial actions on startup 
- Allow deleting components from the editor
- Image frame animation
- Add lv_events.h even if the "Call function" events are not exported 
- Allow editing flex properties in components

### Bugfixes

- Fixing bugs related to components
- Fix the list when right clicking on a widget on a  screen
- Add extern "C" {} to ui_comp.h  
- Add scrollbar style to the panel widget
- Make rendering faster
- Fix disappearing style properties on the screens 
- Fix dropdown styles if they are components

## Version 1.2.1

Release date: 10 Feb 2023

### New features

- 2x timer faster project loading
- Smaller project file size
- Formatted (uncompressed) project file format (JSON)
- Rectangle and round display options- allow adjusting the layouts parameters in components
- Export the UI files too when the a template project is generated
- Save the editor version in the project files 
- Save widget selection in history
- Smart Watch example project

### Bugfixes

- Fix the missing scrollbar on the main area
- Download missing boards if the project was imported (and not created)
- Fix that the widgets couldn't be unlocked after opening the project again
- Fix the reverse widgets order in components during save/reload
- Fix naming issues during component duplication
- Fix exception when moving a component's child
- Fix renaming fonts in components
- Fix file names in "Save as..." in Linux

## Version 1.2.0

Release date: 11 Jan 2023

### Bugfixes

- Fix changing the order of widgets on component editing
- Fix renaming components
- Fix the disappearing images on component generation
- Fix detaching components
- Fix the generated code in SET_TEXT_VALUE_FROM_SLIDER
- Make the launch screen scrollable on small resolutions too
- Fix crating component from the hierachy
- Fix file browser issue with Wayland
- Fix the "hidden" feature
- Fix saving the project settings window
- Fix auto scrolling to the selected widget in the hierarchy panel

### New features

- Portable license option
- Flex layout
- Chart widget
- “lvgl include path” setting in the Project settings
- Scrollbar redesign
- On Zoom In focus on the active screen
- Hotkeys:
  - "a" center the active screen
  - "f" center the selected widget
- Font manager keep the settings from the last generation
- Allow renaming the generated fonts
- Add Keyboard set text area action
- Get board dynamically, on demand from GitHub 
- Add "None" option to Screen change types
- Add padding style option to screen and button widgets
- Add option to whether to add or not the screen name to the new widget 
- Add support for LVGL 8.3.4
- Make it possible to style the list of the drop down widget.

## Version 1.1.1

Release date: 05 Oct 2022

### Bugfixes

- Many fixes for Undo
- Fix memory leak
- Fix renaming the children of components
- Fix moving widgets with large zoom
- Fix Calendar's C export

### New features

- LVGL version selector
- In Preference you you can configure the length of the History
- You can run more SLS instances simultaneously 
- Automatically the Screen name in the default name of the new widgets 
- In Project settings you can configure how to export ui_event file: ui_event.c,  ui_event.cpp or none  

## Version 1.1.0

Release date: 01 Sept 2022

### Bugfixes

- Fix the "Copy" feature in the Hierarchy panel
- Fix the "Eye" (hide) feature in the Hierarchy panel
- Fix non clickable elements on the right side of the screen
- Fix saving the animation parameters when they have been changed.
- Fix incorrectly exported blend mode
- If an image has no alpha channel or all alpha values are 0xFF, generate `LV_IMG_CF_TURE_COLOR` images. If there is alpha channel export with `LV_IMG_CF_TRUE_COLOR_ALPHA` format.
- Make `SET_TEXT_VALUE_WHEN_CHECKED` area multiline and fix `text off`
- Do not allow setting the height of the Text area in one-line mode
- Fix adding assets on MacOS
- Improve peroformace
- Fix export error for drop down list
- Fix export error for slider increment event
- Fix image rotation export error.
- Fix hiding widgets with the eye icon in the hierarchy.
- Fix issue with sing the lock icon
- Fix exporting C code on macOS M1
- Fix exporting the pivot for images
- Save the test object of animations.

### New features

- Error and warning messages are added to the console window
- Add "Force export all images" to project settings to export not only the used images but all images from the assets folder
- Add Espressive boards: ESP-BOX, ESP Wrover Kit
- Check if an image has or hasn't alpha channel and choose the color format accordingly
- Add Open Board Platform
- Add Components
- Auto save
- Add gesture events
- Add an info popup when revoking the license
- Add new animation features
- Add "Check for update at start" checkbox in preferences

## Version 1.0.5

Release date: 28 Marc 2022

### Changes

- Fix freeze on minimize
- Fix missing theme into code in C
- Fix export issue if an image was deleted- Set UI scale to 150% on HiDpi monitors
- Add close button to "project cards" in the launcher
- Improve performance
- Auto-assign new names for child widgets on  copy
- Add CJK character set to font converter (only common characters)
- Update the image selector dropdown on the image widget if a new asset is added
- Trigger Save confirmation popup on animation property change too
- Allow position the selected widget with arrows
- Add support for life-time license
- New example project: Thermostat

## Version 1.0.4

Release date: 11 Marc 2022

### Changes

- Fix typo in the "Ignore layout" flag
- Fix error message when the trial period is over
- Fix the missing option setting in the exported code of Roller and Checkbox
- Fix the missing exported code for the Chart
- Fix overwriting the content of ui_events.c on export
- Include lvgl.h in ui.h in a more flexible way
- In the exported code check if the color settings are correct
- Add "ui_" prefix to the names of the widget in the exported py files to avoid conflict with reserved words

## Version 1.0.3

Release date: 04 Marc 2022

### Changes

- Performance optimization
- Line wrap on all images in ui_images.py
- Fix rare crash when moving widgets in the hierarchy
- Fix the exporting of the CLICKABLE flag on bar widget

## Version 1.0.2

Release date: 23 February 2022

### Changes

- Fix error when loading the POS demo
- "File->Save as..." saves the Assets folder too
- Fix the Save button on the close confirmation pop up
- Show the close confirmation pop up only if there were changes
- On "Save" also save the project into a zip file and keep the last 10 versions 

## Version 1.0.1

Release date: 21 February 2022

### Changes

- In the font manager the name of the fonts can start only with letters and can contain space and numbers
- In the exported user "call function" actions pass the whole event structure as parameter
- Instead of opening the example, create a new project from them
- FOCUSED style is added to all widgets
- Fix typo in the "Scroll direction" dropdown. "Top" was added twice and "Ver" was missing
- Follow the changes in the licensing
- Animations can be renamed
- Collapsed animation panels remain collapsed when a new event is added
