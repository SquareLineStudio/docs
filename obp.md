---
title: Open Board Platform (OBP)
---

# Open Board Platform (OBP)

## OBP Description

The OBP feature allows you to add custom boards to SquareLine Studio. The board packages need to be copied to the **boards** folder of SquareLine Studio. The added boards will be displayed on the Launcher screen in the Create menu.

**OBP file structure:**

```
SquareLine_Studio
└── boards
    └── your_board_name
        └── version (v1_0_0)
            ├── your_board.png
            ├── your_board.zip
            └── your_board.slb
```

## Files

### your_board.png

This image will be shown on Launcher screen.

- Resolution: 380x300px
- File format: PNG, 24 bit

### your_board.zip

It's a zip-ed template project in which you already configured the MCU/MPU, drivers, build system, etc. Basically a whole get-started project from where only the UI files are missing. 
The zip file should contain a folder named `__ui_project_name__` (and not the project files directly).

`lvgl` shouldn't be part of the project as it will be added automatically by SquareLine Studio during exporting.

#### An example ZIP file structure

```
__ui_project_name__
   ├── drivers
   ├── ui
   ├── lv_conf.h
   └── main.c
```

### your_board.slb

A JSON file containing the description and parameters of the board. For example

```
{
    "version":"v1.0.0",
    "group":"SquareLine Studio, LVGL",
    "title": "SLS Board for freeRTOS",
    "keywords": "SLS, freeRTOS, Simulator",
    "width": 480,
    "height": 272,
    "min_width": 16,
    "min_height": 16,
    "max_width": 2048,
    "max_height": 2048,
    "offset_x": 0,
    "offset_y": 0,
    "rotation": 0,
    "color_depth": "16",
    "lvgl_export_path": "packages/LVGL-latest/",
    "lvgl_include_path": "lvgl.h",
    "supported_lvgl_version": "8.2.0, 8.3.2",
    "pattern_match_files": "applications/lvgl/lv_conf.h",
    "language":"C",
    "ui_export_path":"./applications/lvgl/squareline/ui/",
    "url":"https://squareline.io",
    "short_description": "short description",
    "long_description": "long description"
}
```

- `version` - Version of the board.
- `group` - The groups are the button on to of the Create menu of the Launcher screen. You can add a bore more groups. The groups are create dynamically. 
- `title` - Title of the board. It is displayed in the list.
- `keywords` - Will be used for searching (the search is not implemented yet)
- `width` - Default horizontal resolution of the display
- `height` - Default vertical resolution of the display
- `min_width`, `max_width`, `min_height`, `max_height` - Minimal and maximal horizontal and vertical resolution
- `offset_x`, `offset_y` - offset of the screen area
- `rotation` - Supported rotation options: "0, 90, 180, 270"
- `color_depth` - The support color depth options: 8, 16, 16 swapped, 32
- `lvgl_export_path` - The target location of LVGL in the project. If false, 0, or "" lvgl won't be exported.
- `lvgl_include_path` - a path of how to include lvgl. E.g. "lvgl/lvgl.h"
- `supported_lvgl_version` - Supported LVGL versions as a comma separated list. E.g. `"8.1, 8.2"`
- `pattern_match_files` - List of files in which "tags" will be replaced. See the list of supported tags below
- `language` - Programming language ("C" or "Micropython")
- `ui_export_path` - Export the UI files here
- `url` - Link to more info about the board
- `short_description` - Short description of the board
- `long_description` - Long description of the board

#### Tags

These tags can be placed into any file. During exporting a project SquareLine Studio will scan the files pointed by `pattern_match_files` and replace the tags with the actual values.

- `__UI_PROJECT_NAME__` 
- `__UI_PROJECT_HOR_RES__`
- `__UI_PROJECT_VER_RES__`
- `__UI_PROJECT_COLOR_DEPTH__` 
- `__UI_PROJECT_COLOR_16_SWAP__`
- `__UI_LVGL_VERSION_MAJOR__`
- `__UI_LVGL_VERSION_MINOR__`