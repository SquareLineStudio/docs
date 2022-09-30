---
title: Changelog
---

# Changelog

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