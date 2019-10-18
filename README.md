# dynworkspace-handler
dynworkspace-handler is a bash script to switch to workspaces in i3 tiling wm using dmenu  
This script is useful when you use dynamic workspaces in i3, see command example below.

It also can move an complete workspace to an specific output including the feature to identify all available outputs.

# Dependencies
dmenu [workspaces, move to output] (should be available if dmenu is installed)
jq [workspaces, move to output] (tool to parse json in bash)
xterm [move to output] (only if the identify function is used)
figlet [move to output] (only if the identify function is used, makes it pretty)
script needs to be executible

# Configuration
To configure dynworkspace-handler a rc file (~/.config/i3/dynworkspace-handlerrc) is used.
The following settings are possible:
  font="FONT" (default: "xos4 terminus-8")
  monitornames=true|false (default: true)

  font
    - Sets the font used for dmenu

  monitornames
    - enables or disables the output identification via floating xterms 


in i3 (Keyboard shortcut Mod+y to switch, Mod+Shift+y to move active window, Mod+Shift+x to move to specific output)  
  
bindsym $mod+y exec "/path/to/script/dynworkspace-handler"  
bindsym $mod+Shift+y exec "/path/to/script/dynworkspace-handler -m"  
bindsym $mod+Shift+x exec "/path/to/script/dynworkspace-handler -o"

