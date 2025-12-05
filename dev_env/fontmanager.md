---
title: Font manager
---

# Font Manager Panel

Use your operation system fonts in your embedded GUI, as well. LVGL applies UTF-8 encoding to display Unicode characters on any language. Here, you can generate a new font for your GUI project. With the font converter tool, you can create C array from any TTF or WOFF font. You can select ranges of Unicode characters and specify the bpp (bit-per-pixel).

## Create New Font

You can create a new font in the **Create New Font** section. Before creating one, you should copy at least one font into the *Assets/Fonts* folder of the project. You can generate a new font only from those that are listed in the folder.

### Font Name

Here, you can name your font.

### Select Font Asset

You can select the fonts listed in the *Assets/Fonts* folder from a drop-down menu.

### Font Size

You can define the size of the font.

### Bpp

You can define the blur of letter edges in bit per pixel.

### Letters

Letters in the generated font can be selected from an ASCII character list. Default setting is that only those letters are included in the generated font which are selected.

### Range

You can also define custom letter ranges, meaning the ranges and/or characters you would like to include, e.g. 0x20-0x7F, 0x200, 450.

### Symbols

List of characters to include. E.g. ABC0123ÁÉŐ

### Font compression

It reduces size but results in slower rendering.
Compression is more effective with larger fonts and higher bpp. However, it's about 30% slower to render compressed fonts. Therefore, it's recommended to compress only the largest fonts of a user interface, because

- they need the most memory,
- they can be compressed better,
- and probably they are used less frequently then the medium-sized fonts, so the performance cost is smaller.

Learn more [Documentation of LVGL](https://docs.lvgl.io/master/overview/font.html?highlight=font#compressed-fonts).

### Horizontal subpixel rendering

Subpixel rendering allows for tripling the horizontal resolution by rendering anti-aliased edges on Red, Green and Blue channels instead of at pixel level granularity. This takes advantage of the position of physical color channels of each pixel, resulting in higher quality letter anti-aliasing. Learn more [here](https://en.wikipedia.org/wiki/Subpixel_rendering).

Subpixel rendering works only if the color channels of the pixels have a horizontal layout. That is the R, G, B channels are next each other and not above each other. Learn more in the [Documentation of LVGL](https://en.wikipedia.org/wiki/Subpixel_rendering).

> If you specify all parameters, you can create your font by clicking on the **Create Font** button.

## Created Fonts

You can find your fonts here which you can modify or delete, as well.