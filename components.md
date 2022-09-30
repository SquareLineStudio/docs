---
title: Components
---

# Components

A group of widgets (a sub tree in the hierarchy) can be converted to a component. The components are listed below the widgets and can be instantiated like normal widgets.
The components can be edited which will update all instances of the given component. 

The component instances can have local modifications too, that is the original properties can be overwritten on the given instance.

The created components are located in the **components** folder of the project. To remove a component just remove it from the **components** folder. The components of a project can be simply copy-pasted into an other project. 

## Create a new component

Select an already created widget. (It can have children too.) Go to the **COMPONENT** group at top of the inspector panel. 

### Name

It will be the name of component.

### Create

By clicking the create button the component will be created. The instances are shown with purple color in the hierarchy panel to differentiate them from normal widgets. 

To demonstrate how the name of components and their children appear on the hierarchy panel let's take an example: Let's create a Panel widget, and name it like "Main". Add a Button named "Info button" and a  Label on the Button named "Label". Finally create a component from these 3 widgets with the name of "Card". In the hierarchy you will see this. 

```
├── Main (Card)
    ├── Info button (Main)
        └── Label (Main)
```

If we create a new instance of the component it will look like this:

```
├── Main 1 (Card)
    ├── Info button (Main 1)
        └── Label (Main 1)
```

## Edit component

If we select a component on the screen or in the hierarchy we will find two button in the Inspector panel.  található.

### Edit component

By clicking the **Edit component** button the original component cam be edited. The changes will be applied to all the instances of the given component.

### Detach

The **Detach** button convert a component instance back to normal widgets. After that it won't belong to the component.

## Overwrite component parameters

It's possible to add local changes to the component or its children. On the inspector panel the a checkbox appears before the relates parameters. By pressing that checkbox a purple pipe will be shown and the parameter filed after it becomes actives. It indicates that the parameter will overwrite the value comping from the component.

## Export files

When exporting code `ui_comp.c`, `ui_comp.h` for C, or `ui_comp.py` for MicroPython  will be created containing the component related code.

The components created in SquareLine Studio are accessible from code too similarly to normal widgets. To create a component manually call 

- In C: `lv_obj_t * obj = ui_<component_name>_create(parent)` 
- In Micropython: `obj = ui_<component_name>_create(parent)`

After that you reposition, resize, style, delete etc the created component as any widget.

To access the children of the components use

- In C: `lv_obj_t * child = ui_comp_get_child(component_obj, UI_COMP_<COMPONENT_NAME>_<CHILD_NAME>)`
- In Micropython: `child = ui_comp_get_child(component_obj, "<CHILD_NAME>")`

To see the list of the actual children names see `ui_comp.h` or `ui_comp.py`.
