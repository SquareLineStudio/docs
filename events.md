# Events and Actions

Adding events, you can create different interactions to widgets, for instance change the screen, play an animation, etc. by pressing a button.

## Add Event

At the bottom of the [**Inspector**](https://docs.squareline.io/docs/dev_env/inspector) Panel, you can find the **ADD EVENT** button. Firstly, you should name the event, then choose a trigger to start it.

- **Event name** - The name of the event

- **Event Trigger** - The interaction of event start
  
  - **Pressed** - An object has been pressed
  - **Clicked** - An object was pressed for a short period of time, then released. Not called if scrolled
  - **Long pressed** - An object has been pressed for a longer period of time
  - **Long pressed repeat** - Called after `long_press_time` in every `long_press_repeat_time` ms. Not called if scrolled
  - **Focused** - An object is focused
  - **Defocused** - An object is unfocused
  - **Value changed** - The value of the object has been changed.
  - **Ready** - A process has finished
  - **Cancel** - A process has been cancelled
  - **Screen loaded** - A screen was loaded, called when all animations are finished
  - **Screen unloaded** - A screen was unloaded, called when all animations are finished
  - **Screen load start** - A screen load started, fired when the screen change delay is expired
  - **Screen unload start** - A screen unload started, fired immediately when lv_scr_load/lv_scr_load_anim is called
  
  > - **Checked** - A widget chacked állapotba kerül 
  > - **Unchecked** - A widget unchecked állapotba kerül
  > - **Gesture** - A kiváalszott obiektumon a meghatározott irányú gesztus érzékelése

## Add Action

Having added an interaction, you should add an action to be done.

- **Action name** - The name of the action
- **Action type** - The type of the action

## Actions

Actions are those elements of the event, which start when trigger happen.

### Call function

Using the Call function action, you can add a function name that the event can refer to.  This function will be created into the **ui__events.c** or **ui_events.py** file during the exporting process.

### Change Screen

You can change among screens with this action.

- **Screen to** - The screen you would like to change to
- **Fade mode** - The animation during changing the screen
- **Speed** - The speed of changing the screen
- **Delay** - The delay of changing the screen

### Increment Arc

You can modify the value of the Arc Widget.

- **Target** - Target Arc Widget.
- **Value** - The value of increase / decrease

### Increment Bar

You can modify the value of the Bar Widget.

- **Target** - Target Bar Widget
- **Value** - The value of increase / decrease
- **Animate** - The animation time of value change

### Increment Slider

You can modify the value of the Slider Widget.

- **Target** - Target Slider Widget.
- **Value** - Value of increase / decrease.
- **Animate** - The animation time of value change

### Modify Flag

You can modify the flag state of a widget.

- **Object** - The target object
- [**Flags**](https://docs.squareline.io/docs/dev_env/inspector/#flags)  - The defined flag to be changed
- **Action** - The action to be used
  - **Add** - Add a flag
  - **Remove** - Remove a flag
  - **Toggle** - Use a flag from another state

### Play Animation

You can play the animations created in the **Animation Panel**.

- **Animation** - The selected animation
- **Target** - Target widget you would like to use the animation on
- **Delay** - The delay time of the animation

### Set Opacity

The opacity of the selected widget.

- **Target** - The target widget.
- **Value** - The value of opacity.

### Set Flag

Set the value for the flag state of the widget.

- **Object** - The target object.
- **Flag** - The flag to be used.
- **Value** - The value of the flag state.

### Set Property

Change the property value of the widget.

- **Target** - The target object.
- **Property** - The parameter to be changed.
- **Value** - The value of the property.

### Set text value from arc

Display the Arc Widget value on a Label Widget by using this action.

- **Target** - The Label widget to display the value on
- **Source** - The Arc widget value to be displayed
- **Prefix** - The text before the value on the Label widget
- **Postfix** - The text after the value on the Label widget

### Set text value from slider

Display the Slider Widget value on a Label Widget by using this action.

- **Target** - The Label widget to display the value on
- **Source** - The Slider widget value to be displayed
- **Prefix** - The text before the value on the Label widget
- **Postfix** - The text after the value on the Label widget

### Set text value when checked

Change the text of a Label Widget depending on the checked or unchecked state of the target object.

- **Target** - The Label widget to display the text on
- **Source** - The state of the target widget
- **On text** - The text in checked state
- **Of text** - The text in unchecked state