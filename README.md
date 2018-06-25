# VS Code on Windows10 + WSL application (compile and debug)

Main objective of this project is to show the best way of compiling and debug a [WSL](https://docs.microsoft.com/en-us/windows/wsl/about) application.

**NOTE**: cmake tool will be used to compile the project

## Set up your Environment

In order to set your environment please follow the following instructions:

1.  [Enable and install your prefered linux distribution](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
2.  Create a new project and set it up acordingly (use this project as a template)
3.  Build your project
4.  Debug

## Build your Project

The build, for now, is acomplish by using [tasks](https://code.visualstudio.com/docs/editor/tasks) functionality:

So to enable the automatic configuration and build you can add for example the following task to configure:

```
{
    "label": "ReConfigure",
    "type": "shell",
    "command":
    "rm -rf /mnt/c/yourpath/build && mkdir /mnt/c/yourpath/build && cd /mnt/c/yourpath/build && cmake .."
}
```

and then the build task:

```
    {
      "label": "Build",
      "type": "shell",
      "command":
        "cmake --build /mnt/c/yourpath/build",
      "group": {
        "kind": "build",
        "isDefault": true
      }
```

Note that is defined as the default build task, so doing the Ctrl + Shift + B will build the project.

Also note that your are providing the paths to the mounted disk on your WSL system (this to work your vs code integrated terminal must be [configured to use the WSL system desired](https://code.visualstudio.com/docs/editor/integrated-terminal#_windows))

**NOTE**: the desired way should be using the CMake extension... but I can't figure out on how to do that...

## Debug

Debug is acomplish by doing the following: [Windows 10's Windows Subsystem for Linux](https://github.com/Microsoft/vscode-cpptools/blob/master/Documentation/Debugger/gdb/Windows%20Subsystem%20for%20Linux.md)

## Todo's

Use the CMake extension to build the project
