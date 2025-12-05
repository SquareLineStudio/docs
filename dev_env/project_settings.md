---
title: Project settings
---

# Project Settings

There are the settings of your project here.

## Properties

- **Display properties** - Resolution and color depth settings of the project. Allow rotating and offsetting the screen and eectangle and round display options.

- **Object Naming** - With this feature, you can specify prefix options for naming widgets. You can supplement the exported name of a widget with the name of the screen or the type of the widget. Compared to previous versions, if we set the screen name to appear before the widget name and later change the screen name, we no longer need to rename each widget individually.
  
  - **Name** - Given name (prior to version 1.4)
  
  - **Screen_name** - Supplements the given name with the screen name (prior to version 1.4)
  
  - **[Screen]_Name** - Supplements the given name with the screen name and separates them with an underscore.
  
  - **[Screen_Widget]_Name** - Supplements the given name with the screen and widget type names, separated by underscores.
  
  - **[Screen]Name** - Supplements the given name with the screen name.
  
  - **[ScreenWidget]Name** - Supplements the given name with the screen and widget type names.
  
  - **[ScreenWidget]_Name** - Supplements the given name with the screen and widget type names, separated by an underscore.
  
  - **[Widget_Screen]_Name** - Supplements the given name with the widget type  and screen names, separated by an underscore.

- **Custom variable prefix** - Custom variable prefix configuration for Custom variable alias feature

- **Force Exported Names** - to Lower Case By checking this checkbox, all letters will be converted to lowercase during export.

- **Add widget type/subcomponent name to component part define** - Provides backward compatibility for exports with versions prior to 1.5.1.

## Board properties

Select the board, IDE and LVGL version.

## File export

- **Project Export Root** - Path where to export the project template project files.

- **UI Files Export Path** - Path where to export the generated UI files.

- **Project Export Root** - Path where the LVGL library, lvgl.h is located.

- **Multilanguage support** - Select whether the project should support multiple language (translations).

- **Call function export file** - You can choose which file extension the ui_event file is exported with.

- **Force export all images** - Export not only the used images but all images from the assets folder.

- **Flat export** - If Flat export is enabled in Project settings then all the UI files will be exported into a single folder, instead of into screens, fonts, images, etc folders. It might be useful for some build systems (e.g. Arduino) where directories are not processed.

- **Image export mode** -  The image/picture file to load can be located in different places depending on the selected LVGL **fsdrv** drive type:
  
  - For **STDIO**, **POSIX**, **WIN32** simulated drives/partitions, a **drive** folder is created in the exported code, and its subfolder called **assets** contains the images.
  
  - For **FATFS** (and **LittleFS** supported by LVGL-8.3.11) real drives, the dedicated flash partition or an external SD card, etc., can hold the images. You need to copy the **assets** folder from the **drive** folder into the real partition.

- **Export temporary image** - When enabled, exports temporary images for undefined source images.

- **Project description** - You can modify the description of the project given at start.
