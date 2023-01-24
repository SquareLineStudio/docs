---
title: Changelog
---

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
