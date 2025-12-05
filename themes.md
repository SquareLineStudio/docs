---
title: Global colors and themes
---

# Global colors and themes

## Select Theme

You can create global colors and themes for the project. Colors created in the themes panel can be set for any style color parameter. If you change this color, it will change on every widget where it is set. With the provided colors, you can create multiple themes and switch between them with a single action.

- **Selected theme** - You can choose which theme you want to see in the editor from the dropdown menu.
- **Refresh All Screens** - Use this button to manually reload the set colors on the screens.

## Color of Default Theme

In this section, you can create global colors for the default theme. Enter the color name in the **Color name** field and click the **Add Color** button to add it to the list. The color name must be at least 3 characters long.

- **Colors** - The created colors appear in the "Colors" group. If a created color is no longer needed, it can be deleted using the trash can icon.

## Colors of More Themes

Here you can create new themes. Enter the theme name in the **Theme name** field, then create it by clicking the **Add Theme** button. The created theme always contains the colors created in the default theme, and these colors can be overwritten. You can rename the theme in the **Rename** section below the list.

 

# Global Colors and Theme-handling

## Exported code

If you use global colors in SquareLine Studio some additional files will appear in the exported UI-code:

- `ui_theme_manager.c` and corresponding `.h` files which contain the code to use global colors and themes
- `ui_themes.c` and `.h` files which contain the actual color-themes in forms of arrays

## Using colors in code

The global colors you defined in SquareLine Studio are defined in `ui_themes.c` where the names of those arrays start with `_ui_theme_color` and appended with the name of the global color.
The first elements of the arrays are the default global colors. The same goes for alpha-values but with array-names beginning `_ui_theme_alpha`.

## Using themes in code

The atomic function `ui_object_set_themeable_style_property` can set an LVGL style-property to a given value for a given part+state of a widget-object.
In the screen-init functions of `screens` folder it is used in place of `lv_obj_set_style_bg_color` and other similar color/aplha setting functions.
(You can still use those LVGL functions in your extra code but then you need to take care of the indexing for themes, and you'll lose following theme-change for those settings.)

This makes it possible to register atomic style-property settings internally (in `ui_theme_manager.c`) for the arrays of colors mentioned above.
The color that is selected from the color-theme array depends on the value of `ui_theme_idx` variable which determines the selected theme.
(What we call 'theme' here is the whole set of colors/alphas with the given theme-index, in other words, all the values in all the color/alpha arrays of the given position.)

You can still change colour-themes on-the-fly by calling the function `ui_theme_set` function by passing the ID/index of the theme to it.
(Passing `ui_theme_idx` is the most obvious but in case of other value/variable the `ui_theme_idx` will still be updated with the given value.)
Switching the theme will go through all the registered style-property settings made by `ui_object_set_themeable_style_property` earlier.

## Widgets created dynamically

Widgets that are not exported by SquareLine Studio but created by custom code on-the-fly, can still be set to the color of the new theme when `ui_theme_set` is called.
For that you only need to ensure that you use `ui_object_set_themeable_style_property` to set the color/alpha of the created widget.
Arguments you need to pass are:

- `lv_obj_t* object_p` : the widget-object's pointer
- `lv_style_selector_t selector` : The LVGL selector which determines part (e.g. `LV_PART_KNOB`) and state (`LV_STATE_PRESSED`) of the widget-object. See [LVGL documents](https://docs.lvgl.io/8.3/overview/style.html) for more info.
- `lv_style_prop_t property` : The LVGL style-property's name like `LV_STYLE_BG_COLOR` in `lv_style_prop_t` enumeration in LVGL source-code [src/misc/lv_style.h](https://github.com/lvgl/lvgl/blob/release/v8.3/src/misc/lv_style.h).
- `const ui_theme_variable_t* theme_variable_p` : The pointer of the array in `ui_themes.c` which holds the color/alpha themes.

## Example

In many cases you need a dark and a light theme for an application.
For this you can create a white background color and a black foreground color (used for texts/etc.) for a default 'light' theme in SquareLine Studio, and add a black background color and a white foreground color as a second 'dark' theme.
The created arrays in `ui_themes.c` will look like: `const ui_theme_variable_t _ui_theme_color_background[2] = {0xFFFFFF, 0x000000};` `const ui_theme_variable_t _ui_theme_color_foreground[2] = {0x000000, 0xFFFFFF};`

You can then create themeable backgrounds and widgets, in the exported code (e.g. `ui_Screen1.c`) they will look like: `ui_object_set_themeable_style_property( ui_Screen1, LV_PART_MAIN | LV_STATE_DEFAULT, LV_STYLE_BG_COLOR, _ui_theme_color_background );` if you have a screen called `Screen1` `ui_object_set_themeable_style_property( ui_Label1, LV_PART_MAIN | LV_STATE_DEFAULT, LV_STYLE_TEXT_COLOR, _ui_theme_color_foreground );` if you have a label-widget on the screen called `Label1`

From now on you can change the theme between light and dark (e.g. in `main.c` or in `ui_events.c`, wherever you need it) by:

- `ui_theme_set(0);` for light theme or
- `ui_theme_set(1);` for dark theme