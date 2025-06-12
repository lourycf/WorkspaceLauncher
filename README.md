The content under this line is the same as the WorkspaceLauncher-EditWithNotepad.bat file. So you dont even have to download it, but rather just copy and paste.

```
@echo off

:: ==================
:: Workspace Launcher 
:: ==================

:: This file is a little tutorial. You should edit with your paths to make the right launcher for you.

:: >>> Skip to the bottom to see the workflow example



:: (the lines that start with double colons are comments; they don’t affect the script)
:: (lines without the colons are actual commands you type into the .bat file)

:: You’ll need to find the path to the tools and things you use.
:: While we're at it, I can't recommend enough, having the tool Everything 1.5 Alpha installed.


exit
:: ^ This command prevents anything below it from being executed, because the example paths won't work.


:: [1] Set paths ------------------------------------------------------------------------------------------------


::   v 1         v 2
set "projectPath=C:\path\to\project"
:: 1. An arbitrary name as a variable to hold the path, to be called at [2]
:: 2. Place the path of the folder you are using for your project files


::   v 1         v 2
set "gitBashPath=C:\Program Files\Git\git-bash.exe"
:: 1. Another variable name to be called at [2], which holds a path
:: 2. This path points to a file or executable. Instead of a folder, you use it to run/open a file


::   v 1        v 2
set "chromePath=C:\Program Files\Google\Chrome\Application\chrome.exe"
:: 1. Another variable name
:: 2. This is the path to the Chrome executable — probably the same for you too


::   v 1  v 2 
set "url1=https://drive.google.com/drive/my-drive"
:: 1. Just another variable name
:: 2. This is a URL I copied from the Chrome web browser — a site I want to open in my workspace


::   v 1  v 2
set "url2=https://www.youtube.com/watch?v=dQw4w9WgXcQ"
:: 1. Variable name
:: 2. Another example website address


::   v 1           v 2
set "chromeProfile=Profile 5"
:: 1. Variable name as well
:: 2. This points to a Chrome user profile. Needed for opening websites under a specific Chrome user.
::    You can find them at: C:\Users\yourUserName\AppData\Local\Google\Chrome\User Data\Profile (num)
::    You'll have to figure out which number matches the profile you want — maybe by checking the Google Profile.ico inside each folder


::   v 1         v 2
set "blenderPath=C:\Program Files\Blender Foundation\Blender 4.3\blender.exe"
:: 1. Variable name
:: 2. You can also use shortcuts (the ones pinned at Startup, .lnk files)



:: [2] Run paths with params ------------------------------------------------------------------------------------


::         v 1          v 2                   v 3             v 4            v 5
start "" "%chromePath%" --profile-directory="%chromeProfile%" --new-window "%url1%"
:: 0. Notice that all variables are placed between % %
:: 1. This is the variable for your Chrome executable path
:: 2. This param (--profile-directory) launches Chrome under a specific user
:: 3. Insert the variable for the profile number you found
:: 4. This param opens the website in a new window, not just a tab
:: 5. Place the website address variable here


::                                                                           v 1
start "" "%chromePath%" --profile-directory="%chromeProfile%" --new-window "%url2%"
:: 1. Launching another website in a new window using the same Chrome profile


::       v 1        v 2
start "" explorer "%projectPath%"
:: 1. This is a default command to launch File Explorer
:: 2. Opens the path specified earlier


::         v 1           v 2    v 3
start "" "%gitBashPath%" --cd="%projectPath%"
:: 1. Calling the Git Bash executable path
:: 2. Passing the parameter to change directory, cd
:: 3. To the project path you specified


::         v 1
start "" "%blenderPath%"
:: 1. Here I’m launching Blender. If you want to open under a project, set the variable to the path of the .blend project file


:: -------------------------------------------------------------------------------------------------------------------
:: You may delete all this stuff (leave @echo off if you don't want to see the commands when launching your workspace)
:: Or you can keep this file as a reference. Remember to rename your WorkspaceLauncher text file to ".bat" at the end
:: Then, you can place your WorkspaceLauncher.bat file on your desktop or in your project folder
:: -------------------------------------------------------------------------------------------------------------------


:: Some other examples...

set "vscodePath=C:\Users\yourUserName\AppData\Local\Programs\Microsoft VS Code\Code.exe"
set "someCodeProjectFolder=C:\path\to\your\projectFolder"
start "" "%vscodePath%" "%someCodeProjectFolder%"


set "notepadPath=C:\Windows\system32\notepad.exe"
set "someFile=C:\path\to\your\file.txt"
start "" "%notepadPath%" "%someFile%"


set "pythonPath=C:\Users\yourUserName\Envs\myenv\Scripts\python.exe"
set "scriptPath=C:\Users\yourUserName\Scripts\run_this.py"
start "" "%pythonPath%" "%scriptPath%"


:: -------

:: Workflow example:

:: 1. Right click at File Explorer > New > Text Document (Or duplicate a template .txt of yours)

:: 2. Rename to a workspace launcher name you want, like "LetsGoProjWS" or something. Open the txt to edit it.

:: 3. Place your [set "varName=path"]s and [start "" "varName" "param"]s lines. I recommend also having the @echo off at the top

:: 4. While at the notepad, do a Ctrl+Shift+S to save as and add to the end of its name the .bat. A .bat will appear at the same dir, thats your launcher.

:: 5. Place the .bat workspace launcher wherever fits better. 

:: 6. You can always Right Click > Edit with Notepad on your Launcher.bat to edit it
```
