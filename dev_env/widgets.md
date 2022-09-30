---
title: Widgets
---

# Widget panel

You can find widgets, which are the basic elements of UI, on the **Widget Panel**. Every widget has its own preference. You can add custom styles to widget components and you are allowed to configure them in different states.

## Screen

Screen is the main object. It defines the resolution of the work space and widgets can be added here. You can create several screens to your project. To switch among screens, you should use [**Screen Change**](https://docs.squareline.io/docs/events#change-screen) event.

***Style part***

- **Main**

## Basic widgets

Basic widgets category includes main components. These are the most important elements of the screen.

### Arc

You can draw an arc or create an interactive circle slider by using **Arc widget**. The arc consists of three elements:

- **Background** - The background of the arc
- **Indicator** - Using the arc as a curved bar, it indicates its value
- **Knob** - Using the arc as a curved slider, it gives a knob to the slider

***Parameters of Arc Widget***

- **Range min, max** - It defines the minimum and maximum values of the arc
- **Value** - Starter value
- **Bg start, end angle** -  Start / End angle of the background in degrees
- **Start, end angle** - Start / End angle of the indicator in degrees
- **Mode** - You can choose from 3 different modes.
  - **Normal** - The indicator arc is drawn from the minimum value to the current.
  - **Reverse** - The indicator arc is drawn counter-clockwise from the maximum value to the current.
  - **Symmetrical** - The indicator arc is drawn from the middle point to the current value.
- **Rotation** - An offset to the 0 degree position can be added

***Style parts***

- **Main**
- **Indicator**
- **Knob**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_arc_1&w=320&h=240" ></iframe>

### Button

Button is a basic object. By using it, you can create a button fast and easily.

***Style part***

- **Main**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_event_1&w=320&h=240" ></iframe>

### Image

By using **Image** widget, images in the Asset folder are displayed. There are two options to display the images in the Asset folder. You can add an **Image widget** to the screen and set the image to be displayed or you can simply drag the preferred image from the Asset folder to the screen therefore it will appear automatically. 

***Parameters of Image Widget***

- **Asset** - You can select the image to be displayed on the widget from the image list in the Asset folder.
- **Pivot X, Y** - Pivot is the rotation and zoom center of the image.
- **Rotation** - Rotation angle in degrees.
- **Scale** - Scale for zooming in or out.

***Style part***

- **Main**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_img_3&w=320&h=240" ></iframe>

### Label

By using a **Label Widget**, you can add text to the screen.

***Parameters of Label Widget***

- **Label mode** - You can choose different solutions for too long lines.
  - **Wrap** - Wrap too long lines.
  - **Dot** -  Replaces the last 3 characters from the bottom right corner of the label with dots.
  - **Scroll** - If the text is wider than the label, scroll it horizontally back and forth. If it's higher, scroll vertically. Only one direction is scrolled and horizontal scrolling has higher precedence.
  - **Scroll circular** - If the text is wider than the label, scroll it horizontally continuously. If it's higher, scroll vertically. Only one direction is scrolled and horizontal scrolling has higher precedence.
  - **Clip** - Clip the end of the text if the text is wider than the label.
- **Text** - You can add the text to be displayed.
- **Recolor** - In the text, you can use commands to recolor parts of the text. For example: `"Write a #ff0000 red# word"`. 

***Style part***

- **Main**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_label_1&w=320&h=240" ></iframe>

### Panel

Panel Widget is a basic object. By using it, you can create a rectangle which can be transformed freely with styles. You can make rounded corners or add background color, shadows, borders, etc.

***Style parts***

- **Main**
- **Scrollbar**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_obj_1&w=320&h=240" ></iframe>

### Text Area

Text Area is a [Basic object](https://docs.lvgl.io/master/widgets/core/widgets/obj) with a [Label](https://docs.lvgl.io/master/widgets/core/label.html) and a cursor on it. Texts or characters can be added to it. Long lines are wrapped and when the text becomes long enough, the Text Area can be scrolled.

***Parameters of Text Area Widget***

- **Placeholder** - Unique to Text Area, it allows styling the placeholder text.
- **One line mode** - The Text Area can be configured to be a single line. In this mode the height is set automatically to show only one line, line break characters are ignored, and word wrapping is disabled.
- **Password mode** - Text Area works like a password area. Characters are replaced by stars.
- **Accepted characters** - You can set a list of accepted characters. Other characters will be ignored.
- **Max text length** - The maximum number of characters can be limited.

***Style parts***

- **Main**
- **Selected**
- **Cursor**
- **Placeholder**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_textarea_1&w=320&h=240" ></iframe>

## Controller widgets

Here, you can find widgets for controlling.

### Calendar

Calendar Widget is a classic calendar which can:

- show the days of any month in a 7x7 matrix
- show the name of the days
- highlight the current day (today)
- highlight any user-defined dates

***Parameters of Calendar Widget***

- **Day, Month, Year** - You can define the default date with these parameters.

***Style parts***

- **Main**
- **Scrollbar**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_calendar_1&w=320&h=240" ></iframe>

### Checkbox

Checkbox Widget consists of a "tick box" object and a label. When Checkbox Widget is clicked, tick box is toggled.

***Parameters of Checkbox Widget***

- **Title** - The name of the checkbox displayed next to it.

***Style parts***

- **Main**
- **Indicator**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_checkbox_1&w=320&h=240" ></iframe>

### Colorwheel

As its name implies, *Color wheel* allows the user to select a color. The Hue, Saturation and Value of the color can be selected separately. Long pressing the object, the color wheel will change to the next parameter of the color (hue, saturation or value). A double click will reset the current parameter.

***Parameters of Colorwheel Widget***

- **Mode** - You can choose from three color select modes:
  - **Hue** - Full color scale
  - **Saturation** - Saturation of the selected color
  - **Value** - Darker / Lighter version of the selected color

***Style parts***

- **Main**
- **Knob**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_colorwheel_1&w=320&h=240" ></iframe>

### Dropdown

Drop-down Widget is a list that allows the user to select one value from a list.

The drop-down list is closed by default and displays a single value or a predefined text. When activated (by clicking on the drop-down list), a list is created from which the user may select one option. When the user selects a new value, the list is deleted again and displays only the selected value.

The Drop-down list is added to the default group (if it is set). Besides the Drop-down list is an editable object to allow selecting an option with encoder navigation too.

***Parameters of Dropdown Widget***

- **Options** - Options are passed to the drop-down list as a string. You can create enlisted elements by adding new lines to the list.
- **List align** - Position of the list
- **Show selected** - It shows selected elements.
- **Base text** - This text appears by default.
- **Maximum Height** - The maximum height of the list in pixels.

***Style parts***

- **Main**
- **List**
- **Selected**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_dropdown_2&w=320&h=240" ></iframe>

### Image button

The Image button is very similar to the simple 'Button' object. The only difference is that it displays user-defined images in each state instead of drawing a rectangle. You can set a left, right and center image, and the center image will be repeated to match the width of the object.

***Parameters of Image Button Widget***

- **Button state** - Here you can select the state in which you would like to display the image.
  - **Released**
  - **Pressed**
  - **Disabled**
  - **Checked Released**
  - **Checked Pressed**
  - **Checked Disabled**
- **Image released** - You can select an image to the released state.

***Style parts***

- **Main**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_imgbtn_1&w=320&h=240" ></iframe>

### Keyboard

Keyboard allows you to create a virtual keyboard on the screen.

***Parameters of Keyboard Widget***

- **Target text area** - Keyboard Widget is a special [Button matrix](https://docs.lvgl.io/master/widgets/core/btnmatrix.html) with predefined keymaps and other features to realize a virtual keyboard to write texts into a [Text area](https://docs.lvgl.io/master/widgets/core/textarea.html).
- **Mode** - The Keyboards have the following modes:
  - **Text lower** - Display lower case letters
  - **Text upper** - Display upper case letters
  - **Text special** - Display special characters
  - **Number** -  Display numbers, +/- sign, and decimal dot
  - **User 1-3** - User-defined modes

***Style parts***

- **Main**
- **Scrollbar**
- **Items**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_keyboard_1&w=320&h=240" ></iframe>

### Roller

Roller allows you to simply select one option from a list by scrolling.

***Parameters of Roller Widget***

- **Options** - Options you can select from the Roller list. You can create enlisted elements by adding new lines to the list.
- **Text align** - Position of the texts
- **Mode** - Switch between normal and infinite modes
  - **Normal** - You can roll from start to end
  - **Infinite** - You can reroll the list
- **Visible row count** - Setting the number of elements shown in the list
- **Anim time** - It defines the anim time during switching between the elements.

***Style parts***

- **Main**
- **Selected**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_roller_1&w=320&h=240" ></iframe>

### Slider

The Slider Widget looks like a [Bar](https://docs.lvgl.io/master/widgets/core/bar.html) supplemented with a knob. The knob can be dragged to set a value. Just like Bar, Slider can be vertical or horizontal.

***Parameters of Slider Widget***

- **Min, Max** - To specify the range (min, max values)
- **Mode** - The slider can be one of the following modes:
  - **Normal** - A normal slider as described above
  - **Symmertical** - Draw the indicator form the zero value to current value. Requires negative minimum range and positive maximum range.
  - **Range** - Allows setting the start value too. The start value has to be always smaller than the end value.
- **Value** - Defines the current value of the slider.
- **Value left** - Defines the current value of the other knob of the slider.

***Style parts***

- **Main**
- **Indicator**
- **Knob**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_slider_1&w=320&h=240" ></iframe>

### Switch

Switch widget looks like a little slider and can be used to turn something on and off.

***Parameters of Switch Widget***

- **Anim time** - Defines the animation time between on and off states.

***Style parts***

- **Main**
- **Indicator**
- **Knob**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_switch_1&w=320&h=240" ></iframe>

## Visualiser widgets

Visualiser widgets are those elements that are for displaying.

### Bar

The bar widget has a background and an indicator on it. The width of the indicator is set according to the current value of the bar. Vertical bars can be created if the width of the object is smaller than its height. Not only the end, but also the start value of the bar can be set, which changes the start position of the indicator.

***Parameters of Bar Widget***

- **Min, Max** - To specify the range (min, max values).
- **Value** - Defines the current value.
- **Animate** - Changes into the new value with an animation.
- **Anim time** - Defines animation time.

***Style parts***

- **Main**
- **Indicator**

<iframe width="324" height="244" src="https://docs.lvgl.io//8.1/_static/built_lv_examples?example=lv_example_bar_1&w=320&h=240" ></iframe>

### Chart

Charts are a basic objects to visualize data points. Currently *Line* charts (connect points with lines and/or draw points on them) and *Bar* charts are supported. Chart Widgets have limited functions in the editor.

Charts can have:

- division lines
- 2 y axis
- axis ticks and texts on ticks
- cursors
- scrolling and zooming

***Style parts***

- **Main**
- **Items**
- **Indicator**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_chart_3&w=320&h=240" ></iframe>

### Spinner

The Spinner object is a spinning arc over a ring.

***Style parts***

- **Main**
- **Arc**

<iframe width="324" height="244" src="https://docs.lvgl.io/8.1/_static/built_lv_examples?example=lv_example_spinner_1&w=320&h=240" ></iframe>