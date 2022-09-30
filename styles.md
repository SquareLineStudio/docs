# Styles

You can create a custom style to every widget. Using styles, you can define how a widget and its elements look like and which effects are in use.

## Arc

Arc Style can be used in those widgets which have the Arc component.

- **Line color** - The color of the line
- **Arc width** - The width of the arc
- **Arc rounded** - The ends of the arc line are rounded
- **Arc image** - The background image for the arc line

## Background

Background Style is the background of the widgets. You can create gradients or make the corners of the background rounded.

- **Color and alpha** - Set the background color and alpha of the object.
- **Gradient color** - Set the gradient color of the background.
- **Bg main stop** - Set the point from which the background color should start for gradients.
- **Bg gradinet stop** - Set the point from which the background's gradient color should start
- **Bg radius** - The radius you use to make the background corners rounded
- **Gradient direction** - The direction of the gradient. It can be horizontal or vertical.
- **Clip corner** - Enable to clip the overflowed content on the rounded corner.

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_style_2&w=320&h=240" ></iframe>

## Background Image

You can set an image as a background image.

- **Bg image** - The image you use as a background image
- **Bg image opa** - The opacity of the background image
- **Recolor** - With Recolor function, you can use a color on the background image. Set the color depth by changing the alpha parameter.
- **Bg image tiled** - If enabled, background image will be tiled

<iframe src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_style_6&w=320&h=240" width="324" height="244"></iframe>

## Blend

By using Blend Style, you can mix the pixel colors of the current widget part with the colors of the object followed by.

- **Blend mode** - Choose from four options.
  - **Normal** - Default state
  - **Additive** - Adding up pixels
  - **Subtractive** - Subtract pixels
  - **Multiply** - Multiply pixels
- **Blend opacity** - Here you can set the opacity of the widget part

## Border

Using Border, you can draw a border around the selected object onto the inner lines.

- **Border color** - The color of the border
- **Border width** - The width of the border
- **Border side** - The direction of the border

<iframe src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_style_3&w=320&h=240" width="324" height="244"></iframe>

## Line

Line Style can be used in those widgets which have the Line component.

- **Color** - The color of the line
- **Width** - The width of the line 
- **Line rounded** - The ends of the line will be rounded

## Outline

Outline style is similar to Border style but here you draw the border around the selected widget part.

- **Outline color** - The color of the outline
- **Outline width** - The width of the outline
- **Outline pad** - Distance from the side of the widget in pixels

<iframe src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_style_4&w=320&h=240" width="324" height="244"></iframe>

## Paddings

Paddings style put a padding onto the widget part. It means parts under it in the hierarchy will shift by the distance defined in the padding with pixel values.

- **Pad** - The extent of the padding
- 

## Shadow

Using a Shadow Style, you can draw a shadow or a glow to the selected widget part.

- **Shadow color** - The color of the shadow
- **Shadow width** - The width of the shadow
- **Shadow spread** - The depth of the shadow
- **Shadow OX** - Shift the shadow on the X axis
- **Shadow OY** - Shift the shadow on the Y axis

<iframe src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_style_5&w=320&h=240" width="324" height="244"></iframe>

## Text

Text Style defines the parameters of the text that can be found on the widget.

- **Text color** - The color of the text
- **Letter spacing** - The space between the letters
- **Line spacing** - The space between the lines
- **Text align** - The direction of text alignment
- **Text decor** - You can overline or underline the text
  - **None** - Normal text
  - **Understand** - Underlined text
  - **Strikethrough** - Overlined text
- **Text font** - The font of the text
