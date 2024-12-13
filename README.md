# dynworkspace-handler(-sway)
dynworkspace-handler is a bash script to create, swtich to and move windows to workspaces in tiling window managers (sway,i3) using dmenu or the wayland alternative.

dynworkspace-handler is a bash script to switch to workspaces in i3 tiling wm using dmenu.  
This script is useful when you use dynamic workspaces in i3, see command example below.

It also can move an complete workspace to an specific output including the feature to identify all available outputs.

To configure dynworkspace-handler a rc file (~/.config/i3/dynworkspace-handlerrc) is used.  
The following settings are possible:  
  font="FONT" (default: "xos4 terminus-8")  
  monitornames=true|false (default: true)

  font  
    - Sets the font used for dmenu,wofi

  monitornames  
    - enables or disables the output identification via floating xterms 

# Dependencies
dmenu - only i3 [workspaces, move to output]
wofi - only sway [workspaces, move to output] 
jq [workspaces, move to output] (tool to parse json in bash)  
xterm [move to output] (only if the identify function is used)  
figlet [move to output] (only if the identify function is used, makes it pretty)  
script needs to be executible  

# Configuration
When you follow this documentation the following shortcuts do:
  * Mod+y to switch to a workspace
  * Mod+Shift+y to move active window to a workspace
  * Mod+Shift+x to move to specific output)
type to filter, if you hit enter when no filter matches the entry will be created.

## sway
bindsym $mod+y exec "/home/sschoerg/Applications/dynworkspace-handler/dynworkspace-handler-sway"
bindsym $mod+Shift+y exec "/home/sschoerg/Applications/dynworkspace-handler/dynworkspace-handler-sway -m"
bindsym $mod+Shift+x exec "/home/sschoerg/Applications/dynworkspace-handler/dynworkspace-handler-sway -o"

## i3
bindsym $mod+y exec "/path/to/script/dynworkspace-handler"  
bindsym $mod+Shift+y exec "/path/to/script/dynworkspace-handler -m"  
bindsym $mod+Shift+x exec "/path/to/script/dynworkspace-handler -o"

