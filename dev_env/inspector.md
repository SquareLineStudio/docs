---
title: Inspector
---

# Inspector Panel

In the Inspector Panel, there are the parameters of the selected widgets. You can add styles and events to them.

## Widget Properties

All widgets have obligatory parameters, such as name, transformation, flags and states.  Besides, there may be special settings, as well.

### Name

You should name the widget.

> There cannot be a number, underscore or a special character at the beginning of the name. Having exported the code, you can find the widget by that name.

## Layout

You can use a layout to automatically arrange the children of a widget. If the layout is enabled the children's X and Y value can't be adjusted manually, unless the `IGNORE_LAYOUT` or the `FLOATING` flag is enabled on the children.  

- **Layout type** - Select he layout you want to use
- **Flex flow** - Row or column layout.
- **Wrap** - Enable/Disable whether to start a new row/column if the children don't fit.
- **Reverse** - Whter the start with first or last children.
- **Main dir. align** - Alignment in the direction of the flow
- **Cross dir. align** - Alignment in the direction perpendicular to the flow 
- **Track align** -  The alignment of the tracks

The Pad Row and Column values sets the distance between the children in the respective directions.

### Transform

You should define the position and size of every widget and its alignment to its own parent. 

- **X, Y** - The X and Y position of the widget.
  
  > This value can be added in pixels or in percents. Percent value will refer to the size of the parent widget.

- **Width, Height** - The width and height of the widget.
  
  > This value can be added in pixels, percents, or the content can define the parameters. Percent value will refer to the size of the parent widget, the content will copy the maximum size of the children widgets.
  > 
  > If the parent has Flex layout the children's width/height can be set in **fr** unit as well. It tells how much space to take proportionally from the free space in a track. 

- **Align** - The alignment of the widget to the parent.

### Flags

Flags are different attributes, connected to the widgets, which can be enabled or disabled.

#### Main Flags

- **Hidden** - Make the object hidden. (Like it wasn't there at all.)
- **Clickable** - Make the object clickable by input devices
- **Click focusable** - Add focused state to the object when clicked
- **Checkable** - Toggle checked state when the object is clicked
- **Snappable** - If scroll snap is enabled on the parent it can snap to this object
- **Press lock** - Keep the object pressed even if the press slid from the object
- **Event bubble** - Propagate the events to the parent too
- **Gesture bubble** - Propagate the events to the parent too
- **Adv hittest** - Allow performing more accurate hit (click) test. E.g. accounting for rounded corners
- **Ignore layout** - Make the object positionable by the layouts
- **Floating** - Do not scroll the object when the parent scrolls and ignore layout

#### Scroll Flags

- **Scrollable** - Make the object scrollable
- **Scroll elastic** - Allow scrolling inside but with slower speed
- **Scroll momentum** - Make the object scroll further when "thrown"
- **Scroll one** - Allow scrolling only one snappable children
- **Scroll chain** - Allow propagating the scroll to a parent
- **Scroll on focus** - Automatically scroll object to make it visible when focused

#### Scroll Settings

- **Scroll direction** - Scrollbars are displayed according to a configured
- **Scrollbar mode** - Scrollbars are displayed according to a configured `mode`. The following `mode`s exist:
  - **Off** - Never show the scrollbars
  - **On** - Always show the scrollbars
  - **Active** - Show scroll bars while a object is being scrolled
  - **Auto** - Show scroll bars when the content is large enough to be scrolled

### States

The object can be in a combination of the following states:

- **Clickable** - Toggled or checked state
- **Disable** - Disabled state
- **Focusable** - Focused via keypad or encoder or clicked via touchpad/mouse
- **Pressed** - Being pressed

## Style settings

Styles can be used to add effects to widgets or their parts. You can add a custom background color, border, shadow, etc. In Style Settings, you can add or modify the values of these parameters. 

### State

You can create a custom style to each state.

### Style Properties

Style Properties are the parameters to be set for the styles.

[**Styles**](/docs/styles)  - More information on styles in the Styles section

### Event Properties

[**Event**](/docs/events)  - More information on events in the Event section
