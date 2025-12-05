---
title: Commandline Export
---

# Commandline Export

## Commandline arguments

In some cases it's desirable to automatize the simple project-file tasks like opening and exporting/converting projects.
For example when your SquareLine Studio project is a part of a larger build or you have more UI-projects to build at once with a bash/shell script.
SquareLine Studio can now receive several commandline arguments to make this possible. If you use these arguments you don't need to open the GUI and manually open projects.

> The commandline interface/automation doesn't work (stops at startup just like the GUI) if you don't have a licence that was set already in the GUI. So first log in with your licence in the GUI to save your credentials for upcoming runs.

## The possible SquareLine Studio arguments:

- To open a project from the command line you can give the path and filename of the SquareLine `.spj` project with `-projectfile <path and filename>` argument. This can be used for file-associations on your operating system.

- To export a project in command-line you need to give the project-file as described above, and you also need to pass an other argument `-exportfolder <path and folder>` giving the export-folder.

- In case you only want to export/refresh the `ui` folder of the exported project, you need to add yet another argument `-ui_exportfolder <path and 'ui' folder>` giving the ui folder to save. (Export-folder should still be given to know where to save `lv_conf.h`.)

> You can use both relative and absolute paths, whatever your script requires. If the path contains any space characters you need to put the path between `""` double quotes. 

SquareLine Studio can receive some general Unity arguments too which might be usable for you:

- The argument `-logFile -` gives more verbose results on the commandline with some useful feedback from SquareLine Studio
- The argument `-batchmode` tries to disable the GUI so you can see the commandline information during the process. (There are other similar Unity modifiers like `-nographics` and `-popupwindow` trying to do the same.)

## Example

Let's say you're in the SquareLine Studio folder on Linux, where you can find the program's executable file, and you have a project in that folder called `ExampleProject` with the default project-name `SquareLine_Project`.
To open the project from commandline you can type:
`./SquareLine_Studio.x86_64  -logFile -  -projectfile "./ExampleProject/SquareLine_Project.spj"`

You can export the project into a folder called `export` (without opening SquareLine Studio GUI) by the command:
`./SquareLine_Studio.x86_64  -batchmode  -projectfile "ExampleProject/SquareLine_Project.spj"  -exportfolder "ExampleProject/export"`
This will take some time (at least about 3 seconds) depending on the size of the project. If there's an export already at the target folder it will be overwritten.

You can export (and overwrite) the `ui` folder with:
`./SquareLine_Studio.x86_64  -batchmode  -logFile -  -projectfile "ExampleProject/SquareLine_Project.spj"  -exportfolder "ExampleProject/export"  -ui_exportfolder "ExampleProject/export/SquareLine_Project/ui"`

> You need to have an existing export-folder already to do this.
