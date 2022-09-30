---
title: Tutorial 2 - Create a new application
---

# Tutorial 2 - Create a new application

With this tutorial, you can learn how to create a new project, a screen or a widget.

## Creating a new project

Having the software launched, a [**Launcher**](https://docs.squareline.io/docs/dev_env/launcher) window will pop up. You should choose **Create** menu. Here you can find the **Simulator** and the purchased **Board**s, as well. By choosing a ****Board****, the program will automatically set the resolution and the color depth for the project and it will also add the drivers needed. By choosing **Simulator**, you can set both the resolution and the color depth.  The maximum resolution of your project can be 2048 x 2048 pixels. The default resolution setting is 280x320 pixels. Having set everything, you should select the name and the path of your project, then you have nothing else to do but to click on **CREATE NEW PROJECT** button.

## Create a button

After creating a project, a **Screen** will be automatically added.

- On the [**Widget Panel**](https://docs.squareline.io/docs/dev_env/widgets), please click on the [**Button**](https://docs.squareline.io/docs/dev_env/widgets#button) widget or you can also drag it on the **Screen**. Its position should be set on the following values: **X=0, Y=80**.

- Then you can add a [**Label**](https://docs.squareline.io/docs/dev_env/widgets#label) widget to the **Screen**. Its position should be set on the following values: **X=0, Y=0**. 
  
  - Click on *STYLE SETTINS / STYLE (MAIN) / Text / Text Align* on the [**Inspector Panel**](https://docs.squareline.io/docs/dev_env/inspector) and set it to center. By doing this, the text will be aligned to center inside the text box.
  
  - Click on *Text align* section and choose **Montserrat 16** font.
  
  - The height of the text box should be set to **20 px** in the *Transform* section.
  
  - Change the text in the *Text* section to **Next**.

- Then, click and hold the left mouse button on **Label** in the [**Hierarchy Panel**](https://docs.squareline.io/docs/dev_env/hierarchy) and drag it on the list to **Button** until the item on the list moves to the right.  It means the selected item will be under **Button** in the hierarchy. Now you can release the left mouse button. By doing so, the text aligns automatically to the center of the button, copying its style. That's why the color of the text changes to white.

## Add an image asset

You can add a **PNG** format image to the project with the size of maximum **2048x2048 px**.

- Choose the [**Asset Panel**](https://docs.squareline.io/docs/dev_env/assetes) then click on the **ADD FILE INTO ASSETS** button. Add the downloaded image to the appearing file browser to make it show in the **Asset Panel**. Drag the image to the screen from the **Asset Panel**. Since most recent widgets always go to the top, drag the image above the button. Now you can see the previously created button.

## Add new screen

Click on the **Screen widget** on Widget Panel to add a new screen to the project. It shows up next to the previous screen with a green color on the **Hierarchy Panel** signalling that we are editing the new screen.

- Add a new image just like you did it before.

- Select the button on the first screen on the **Hierarchy Panel**. Having selected it, three icons appear in the list. Click on the last one which is for duplicating. Drag the new button under the image added to the other screen. Now the button appears on the new screen.

- Change the **Label** of the button to Back.

- Select the button and change **Align** from **Center** to **Top Left**. Then change its position to **X=20, Y=20**. Now the button on the second screen appears in the top left corner.