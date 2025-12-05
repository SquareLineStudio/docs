---
title: Multilanguage
---

# How to create a multilingual app?

To create a multi language UI you need to enable the multi language support in the project settings. You can change it at any time.

If it's enabled all text fields on the inspector panel will have a **To be translated** checkbox. If this checkbox is checked special code will be exported for that text. 

### Exported code

If you have enabled multi language support you need to manually add and use the `lv_i18n` library in your project. If the **To be translated** checkbox is checked for a text, the text will be exported like `_("text")`. From this notion the [**lv_i18n**](https://github.com/lvgl/lv_i18n)  library will know that this text needs to be translated and LVGL will retrieve the translated version of the text. 

To learn more about the usage of lv_i18n check out its [**README**](https://github.com/lvgl/lv_i18n/blob/master/README.md).