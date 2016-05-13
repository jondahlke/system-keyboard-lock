# System Keyboard Lock
API that allows websites to capture and use reserved keys and keyboard shortcuts.

See [EXPLAINER](https://github.com/jondahlke/system-keyboard-lock/blob/master/EXPLAINER.md) for proposed solution.

## Problem
Richly interactive web sites, games and remote desktop/application streaming experiences want to provide an immersive, full screen experience. Sites need access to special keys and keyboard shortcuts in full screen, such as Escape, Alt+Tab, Cmd+`, Ctrl+N, for easily or efficiently navigating through windows, tabs, applications, menus and gaming functionality. Today this isn’t possible, as these keys are typically captured by the browser or underlying operating system, making it challenging for developers to embrace the web for these types of applications. This repo explores ideas for a new system keyboard lock API, that enable websites to capture and use all available keys and keyboard combinations allowed by the OS.

## Use Cases 
1. A developer is working from home and wants to remote into their development PC at work. The user opens a web-based remote    desktop application to connect to the remote device. All the browser and OS shortcuts, such as Cmd/Alt+Tab could be used     to switch windows on the remote computer, while Escape can be used to cancel a command. 
2. A user is playing Call of Duty over a streaming game service. In the game, the Escape key can be used to access the menu.
3. A user is playing a rich, web-based immersive game in full screen. The user is able to navigate through the game using       their keyboard and is able to launch and exit menus using the Escape key and use Alt/Cmd+Tab without exiting the browser     or full screen.


