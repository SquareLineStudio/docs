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

There is the "Don't export" checkbox on the right side of widget Group name. When enabled, the widget won't be exported and can be used as temporary or dummy object. Non-exported widgets appear dimmed in the hierarchy panel.

### Custom variable alias

Having consistent variable-names for screens and widgets in an exported SquareLine Studio code, which reflects the semantics and logic of a design, is an essential ingredient for efficient frontend-logic and API programming.

The GUI-object names given by either the designers and SquareLine Studio itself are usually oriented towards aspects of the design and layout, but these details should be hidden away from the programmer, and only the main aspects should be kept in the naming:

- The type of an object (screen / button / label / roller / etc.), so it is easily seen what exact LVGL functions to use on it in the code.
- If it's a screen, its name, or if it's a widget, the screen (and maybe a parent-widget) where it can be found. With a certain amount of complexity it helps a lot to find a widget.
- A meaningful name for the object that ideally reflects the role of it throughout the whole system. This helps the programmers to see the connection between the SquareLine Studio design and the backend functionalities.

#### Introduction

SquareLine Studio already does its best to create automatically assembled names from the designer's intent ('Name' field in the inspector panel) and the design-layout, if a naming-scheme feature is selected in Project Settings (by the dropdown-menu 'Object naming').
For example, by selecting `[Widget__Screen]__Name` format we'll see names like `SpecialButton__Home__SpecialButton1__ButtonLabel`, where 'SecialButton' is a component, 'SpecialButton1' is its auto-named instance.

Due to the nature of the desgin with component and layout oriented hierarchies it isn't always obvious for the designers and SquareLine Studio what is a good name for the programmers, and the name above contains design-related details unnecessary from coding point of view.
It would look more straightforward and meaningful as something like `ButtonLabel__Home__Start` or `Button__Home__Start`, if the role of the button is starting something, we don't care if it's a special-looking component-based button in the design.

On the other hand it would clutter the exported output's 'ui' namespace if every children of every component would be exported by default in ui.h.

Therefore a new feature was added to the Inspector panel right below the 'Name' field: an additional text-entry field called 'Custom variable alias' where the programmer can semi-automatically create a totally custom name tailored for programming in mind.

For widgets and children of components, where this field is used, it will generate a direct object-pointer in ui.h instead of needing to resort to manually programmed bindings for the exported code.

#### Usage

- By default the 'Custom variable alias' field shows the roundabout assembled name that will be exported by default from SquareLine Studio for the widget.

- Pressing the 'FILL' button on the right-hand side once tries to create a name according the naming-scheme selected in Project-settings but allowing to rewrite the last white-coloured part of the name to a more meaningful/exact one.

- If the automatically generated prefixing (coloured grey) is not for the programmer's liking, pressing 'FILL' button again enables modifying the whole name, like the correction of widget-type to more general (not component-name based) and removing component-instance name if it's not needed.

- (Pressing 'FILL' button more times toggles between these two entry modes.)

- Deleting the white-coloured custom name deletes the creation of a custom variable name.
  
  The very first 'uic_' prefix always remaining grey-coloured, is the 'namespace' prefix common for all objects, and cannot be modified here. It can be modified in Projec Settings 'Custom variable prefix' text-entry field.
  The 'uic' default text there is to tell custom names from the others in the export and possibly avoid name-clashes, but 'ui' can still be used there as well as programmers usually don't need to know which names are coming from automatic or manual naming from SquareLine Studio.
  
  In the exported code the custom name declarations are exported into 'ui.h' below the corresponding screen's default GUI-object declarations begginning with comment 'CUSTOM VARIABLES'.

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
- **Scroll with arrow** - Allow scrolling the focused object with arrow keys
- **Overflow visibile** - Do not clip the children's content to the parent's boundary

### Scrolling

The Scrolling section provides comprehensive control over scroll behavior for objects. In this updated interface, scrolling settings have been moved from flags to a dedicated panel section for improved organization and accessibility.

#### Scroll Properties

- **Scrollable** - Enable scrolling functionality for this object
- **Scroll elastic** - Allow scrolling beyond boundaries with resistance (slower scroll speed at edges)
- **Scroll momentum** - Enable inertial scrolling, allowing content to continue scrolling after being "thrown"
- **Scroll on focus** - Automatically scroll to make this object visible when it receives focus
- **Scroll chain** - Allow scroll events to propagate to parent objects when reaching boundaries
- **Scroll with arrow** - Enable scrolling using arrow keys or buttons
- **Scroll one** - Limit scrolling to one snappable child at a time

#### Scroll Configuration

- **Scrollbar mode** - Control the visibility behavior of scrollbars:
  
  - **OFF** - Never display scrollbars
  - **ON** - Always display scrollbars
  - **AUTO** - Show scrollbars only when content exceeds the viewable area
  - **ACTIVE** - Display scrollbars only during active scrolling

- **Scroll direction** - Define which directions scrolling is allowed:
  
  - **TOP** - Allow scrolling only toward the top
  - **LEFT** - Allow scrolling only toward the left
  - **BOTTOM** - Allow scrolling only toward the bottom
  - **RIGHT** - Allow scrolling only toward the right
  - **HOR** - Allow horizontal scrolling (both left and right)
  - **VER** - Allow vertical scrolling (both top and bottom)
  - **ALL** - Enable scrolling in all directions

- **Scroll snap x** - Control horizontal snapping behavior:
  
  - **NONE** - No snapping on the x-axis
  - **CENTER** - Snap children to center position
  - **START** - Snap children to start position
  - **END** - Snap children to end position

- **Scroll snap y** - Control vertical snapping behavior:
  
  - **NONE** - No snapping on the y-axis
  - **CENTER** - Snap children to center position
  - **START** - Snap children to top position
  - **END** - Snap children to bottom position



### States

The object can be in a combination of the following states:

- **Clickable** - Toggled or checked state
- **Disable** - Disabled state
- **Focusable** - Focused via keypad or encoder or clicked via touchpad/mouse
- **Pressed** - Being pressed
- **User 1** - Unique
- **User 2** - Unique
- **User 3** - Unique
- **User 4** - Unique

## Style settings

Styles can be used to add effects to widgets or their parts. You can add a custom background color, border, shadow, etc. In Style Settings, you can add or modify the values of these parameters. 

### State

You can create a custom style to each state.

### Style Properties

Style Properties are the parameters to be set for the styles.

[**Styles**](/docs/styles)  - More information on styles in the Styles section

### Event Properties

[**Event**](/docs/events)  - More information on events in the Event section
