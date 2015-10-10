# dynworkspace-handler
dynworkspace-handler is a bash script to switch to workspaces in i3 tiling wm using dmenu  
This script is useful when you use dynamic workspaces in i3, see command example below.

# Dependencies
The script needs dmenu in the path (should be there when i3 is installed)  
i3  
jq -> tool to parse json in bash  
script needs to be executible  

# Configuration
in i3 to create a dynamic named workspace and move windows to it  
  
bindsym $mod+Control+c exec i3-input -F 'workspace "%s"' -P 'Switch to workspace: '  
bindsym $mod+Shift+Control+c    exec i3-input -F 'move container to workspace %s' -P 'Move to workspace: '  
  
  

in i3 (Keyboard shortcut Mod+y to switch, Mod+Shift+y to move active window)  
  
bindsym $mod+y exec "/path/to/script/dynworkspace-handler"  
bindsym $mod+Shift+y exec "/path/to/script/dynworkspace-handler -m"  

