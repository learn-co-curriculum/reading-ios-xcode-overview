# Xcode: An Overview

# Introduction to Xcode

## Objectives
1. Understand the concept of an Integrated Development Environment.
2. Get oriented with the basic layout of Xcode.

## What is Xcode?

Xcode is the **Integrated Development Environment** (**IDE**) provided by Apple to third-party programmers such as yourself for developing iOS and OS X applications written in Objective-C and Swift. An IDE is a program (or program suite) that incorporates tools for the various aspects of creating software. Xcode, specifically, brings together the code editor, compiler, debugger, interface builder, application bundler, and simulator (which is technically a separate program launched from within Xcode).

**Note:** *The first time you open Xcode, your machine will ask you if you want enable "Developer Mode". Go ahead and do this; don't be scared of it! What it does is allow you to debug your projects without OS X asking for your administrator password every time. If you previously selected "No" the first time you opened Xcode, don't worry! Just open your terminal and type* `$ DevToolsSecurity -enable`.

Let's unpack some of the terminology in that last sentence:

1. **Code Editor** - a text editor that specializes in handling code as text. Sublime Text is a prime example of a standalone code editor.
2. **Compiler** - this is a program that translates your code from Objective-C or Swift into machine language, the native language of the processor. When you hit "Run", your code is first compiled so it can then be handed to your computer's processor to execute. Xcode also contains a **Pre-Compiler** which scans your code *as you type it* for syntactical errors and other problems to reduce the likelihood that your build contains code that will cause a crash.
3. **Debugger** - all code has errors. "Good Practice" guidelines and pre-compilers help reduce the likelihood of errors being written, but they happen. Good debugging tools allow the programmer to scan the code as processes are running, watching the application's elements act upon and change themselves to see where they collide.
4. **Interface Builder** - specifically in Xcode this is the name of the suite that allows the use of Storyboards to create the visual layout of a user interface (UI) in a similar fashion to design and layout software.
5. **Application Bundler** - this assembles the program as an application package to be shipped to the consumer for deployment. You won't be using this for any of the labs, but you should know that Xcode contains the functionality to submit your application to the App Store for review. You might eventually do this on your own with side projects.
6. **Simulator** - Xcode contains a program for partially replicating the conditions of running your application on a mobile device. It's very useful for development to see how your code might behave once it's deployed, but for a variety of reasons it can't ever be quite the real thing so it can't replace testing your build on an actual mobile device.



## Xcode Anatomy 101

**Note:** *If this is your first time using Xcode and would like a sample project to explore, go ahead and fork, clone, and open the lab in the "Objective-C fundamentals" lesson titled* Your-First-NSLog.

In addition to the typically-placed application Toolbar, Xcode has four main workspace windows. These are, in clockwise rotation from the left:

1. The Navigator area,
2. The Editor area,
3. The Utilities area, and
4. The Debug area.

![](https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_overview.png)

## 0. Workspace Toolbar

![](https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_workspace_toolbar.png)

The Toolbar is a small collection of project-wide buttons and labels. They are:

1. Close/Minimize/Maximize Window buttons (these are the red, yellow, and green dots standard to all OS X windows),
2. The ▶︎ "**Run**" button (`⌘` `R`) which builds and then runs the current scheme,
3. The ◼︎ "**Stop**" button (`⌘` `.`) which stops the running scheme or application,
4. The "**Scheme Menu**",
	* The left half selects the current target,
	* The right half selects the destination—the device or simulator you wish to run on, (**Note:** *If you connect an iOS device to your computer, Xcode will typically assume you want to run the build on that device and automatically select it as your destination. If you encounter an authorization error, this may be the cause of it. Selecting the simulator instead will not trigger the authorization check.*

5. The "**Activity viewer**" displays information relevant to the current operation, as well as symbols for the number of warning and errors generated by the compiler,
6. The **Editor configuration buttons**,
	* "**Standard Editor**" - shows the primary code editor window
	* "**Assistant Editor**" - shows a secondary code editor window alongside the primary window (this gets crowded without a larger screen),
	* "**Version Editor**" - shows the Xcode's built-in version control UI, since we utilize git and GitHub for version control, you will not use for the labs,
	
7. The **Workspace configuration buttons** which show or hide their respective areas:

| Icon            | Workspace Configuration Button      |
|:---------------:|-------------------------------------|
| ![][nav_left]   | Show or hide the **Navigator area**.|
| ![][nav_middle] | Show or hide the **Debug area**.    |
| ![][nav_right]  | Show or hide the **Utilities area**.|

###Choosing a Destination

The **Scheme Menu** allows you to select your target and destination with drop-down menus:

![](https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_run_destination.png)


## 1. The Navigator Area

The appropriately-named **Navigator area** is actually a stack of eight different navigators which help you get around your project based on different elements. You'll likely spend the most time with the Project Navigator which is the default drop-down file list.

![](https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_navigator.png)

**Top Tip:** *An easy way to tell if you are in either an* `*.xcodeproj` *file or an* `*.xcworkspace` *file is by looking for multiple "blueprint" icons in the Project Navigator. If you see only one then you are currently inside a* `*.xcodeproj` *file and running a scheme that incorporates outside frameworks like CocoaPods such as Specta & Expecta will fail to build. If you are using CocoaPods and don't see a second "blueprint" icon labeled "Pods", then you need to close your project and open the* `*.xcworkspace` *file instead.*

The folder icons indicate a "group". They are named "groups" instead of "folders" because this is a file structure internal to Xcode and separate from the operating system's file structure which uses directories, a.k.a. folders. You can create a group by going to the Status bar and selecting `File` —> `New` —> `Group` OR `Group From Selection`. Adding a file to a group does NOT move it around in your directory. You will not be making your own groups until later labs, but get used to calling them groups.

| Icon            | Navigator Pane | Description |
|---------------------|:----------:|:------------|
| ![][nav_project]    | Project    | Add, delete, group, and otherwise manage files in your project, or choose a file to view or edit its contents in the editor area.|
| ![][nav_symbol]     | Symbol     | Browse the symbols in your project as a list or hierarchy. Buttons on the left of the filter bar let you limit the shown symbols to a combination of only classes and protocols, only symbols in your project, or only containers.|
| ![][nav_find]       | Find       | Use search options and filters to quickly find any string within your project.|
| ![][nav_issue]      | Issue      | View issues such as diagnostics, warnings, and errors found when opening, analyzing, and building your project.|
| ![][nav_test]       | Test       | Create, manage, run, and review unit tests.|
| ![][nav_debug]      | Debug      | Examine the running threads and associated stack information at a specified point or time during program execution.|
| ![][nav_breakpoint] | Breakpoint | Fine-tune breakpoints by specifying characteristics such as triggering conditions.|
| ![][nav_report]     | Report     | View the history of your build, run, debug, continuous integration, and source control tasks.|

### The Test Navigator

After running a build utilizing your unit tests (`⌘` `U`), the Test navigator will populate itself with your test results. A green light means the test passed, a red light means it failed! Selecting a test by name in this navigator will load that test's file in the Code Editor at the relevant line for the selected test.

![](https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_test_overview.png)

**Note:** *The testing frameworks within Xcode periodically become unstable. If your tests fail when you're reasonably confident that they should be passing, before tearing your code apart try the first step of closing Xcode completely and restarting the application.*

## 2. The Code Editor

This is the window which contains Xcode's text editor for writing code. The font coloring is based upon the syntax of the currently relevant programming language. You can customize these colors and the font type & size of your text in Xcode's preferences under the "**Fonts & Colors**" tab. 

**Top Tip:** *You can also create a presentation preset for easily switching to larger display fonts without affecting your personal font customizations.*

### The Gutter

The left-most column in the Code Editor which contains the line numbers is known as the **Gutter**. Blue arrow-tabs present in the gutter are "**breakpoint indicators**". Breakpoints are a part of the debugging process that we'll teach you about later.

![](https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_debug_breakpoint_gutter.png)  
**Above:** *Xcode when encountering a breakpoint.*
 
The vertical line between the line numbers and your code allows you to fold or unfold your code. **Code folding** is an action that collapses a block or segment of code in the editor to make it easier to read. This feature won't be relevant to you until you get to the more advanced labs, but you should be aware of it in case you invoke it accidentally. Double-clicking on this folding bar will cause the selected block of code to collapse into a pair of curly braces containing an ellipsis `{ ... }`. Don't panic when you do this accidentally! Just click on the ellipsis and your code will expand back out.

## 3. The Utilities Area

The Utilities Area really shines in Interface Builder which we're not introducing to you just yet. In the Code Editor, however, it displays only either the File Inspector or the Quick Help guide.

* The **File Inspector** displays a set of information relevant to the current file such as directory path and target.
* The **Quick Help** guide is immensely helpful. It provides a summary description of the cursor-selected class and several relevant hot links, specifically the link to Apple's Reference Guide on that class. This is often quicker than a google search and works offline, being stored locally as part of Xcode. You can access this database directly in Xcode's status bar by selecting Help —> Documentation and API Reference.

## 4. The Debug Area

The debugger is usually tucked away while writing code, yet comes out to play almost every time the build is run. An automatic breakpoint will get triggered if your build succeeds but your program crashes. The information printed out can be a valuable source of insight toward finding the problem. In time, you'll learn how to interpret much of the information that gets dumped out by a crash!

![](https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_debug_overview.png)


![](https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_debug_area_detail.png)

The left window is the **Variable Viewer** which shows a drop-down list of all of your program's objects and instance variables held in memory at the current scope. We'll teach you how to review the information in this window.

The right window is the **Console Output Viewer**. This is where your `NSLog`s will print out.

We'll teach your more about how to use the debugger effectively in the next unit. For now, just understand the layout of the tools well enough to locate the Console Output viewer. If you can only see the Variable Viewer (or vice-versa), the Console Output Viewer is likely hidden. There's a pair of show/hide buttons in the bottom right corner of the Debug area which governs these two viewers.

| Icon           | Debugger Configuration Button              |
|:--------------:|--------------------------------------------|
| ![][nav_left]  | Show or hide the **Variable Viewer**.      |
| ![][nav_right] | Show or hide the **Console Output Viewer**.|

[nav_left]: https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_workspace_nav_left.png
[nav_middle]: https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_workspace_nav_middle.png
[nav_right]: https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_workspace_nav_right.png

[nav_project]: http://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_project_navigator_table.png
[nav_symbol]: http://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_symbol_navigator_table.png
[nav_find]: http://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_find_navigator_table.png
[nav_issue]: http://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_issue_navigator_table.png
[nav_test]: http://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_test_navigator_table.png
[nav_debug]: http://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_debug_navigator_table.png
[nav_breakpoint]: http://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_breakpoint_navigator_table.png
[nav_report]: http://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_report_navigator_table.png

[hide_debug]: https://curriculum-content.s3.amazonaws.com/reading-ios-debugging/toolbar_hideDebugArea.png
[bkpnt_toggle]: https://curriculum-content.s3.amazonaws.com/reading-ios-debugging/toolbar_toggleBreakpoints_on.png
[debug_play]: https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_debug_play.png
[debug_pause]: https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_debug_pause.png
[step_over]: https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_debug_step_over.png
[step_into]: https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_debug_step_into.png
[step_out]: https://ironboard-curriculum-content.s3.amazonaws.com/iOS/intro-to-xcode/xcode_debug_step_out.png
[view_debug]: https://curriculum-content.s3.amazonaws.com/reading-ios-debugging/toolbar_viewDebugger.png
[loc_sim]: https://curriculum-content.s3.amazonaws.com/reading-ios-debugging/toolbar_locationSimulator.png


<p data-visibility='hidden'>View <a href='https://learn.co/lessons/reading-ios-xcode-overview' title='Xcode: An Overview'>Xcode: An Overview</a> on Learn.co and start learning to code for free.</p>

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/reading-ios-xcode-overview'>Xcode: An Overview</a> on Learn.co and start learning to code for free.</p>

<p class='util--hide'>View <a href='https://learn.co/lessons/reading-ios-xcode-overview'>Xcode: An Overview</a> on Learn.co and start learning to code for free.</p>
