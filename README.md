# Paneblocker tmux
Script to disable/enable input on selected tmux panes. Useful for 'selecting' which panes you want to synchronize without having to synchronize all panes in tmux.

https://github.com/rollerd/paneblocker/assets/4483048/2d252d2a-4f5d-4206-9f76-46652a80944a

### Installation
Download the paneblock script.
Make the file executable (`chmod 755 ./paneblock`).
Copy the paneblock script to a directory that exists in your PATH. (`cp paneblock /usr/local/bin`)

### Usage

##### Panes
`paneblock [-i|e|d|a] <pane_index(es)>`
Call paneblock with the expected 'mode' and target pane indexes. Target indexes are args separated by space.
If using `-i`, the pane index selection will be inverted; ie all panes EXCEPT those specified.
Examples:

```
# Disable input on panes 0,4,6:
paneblock -d 0 4 6

# Enable input on pane 4:
paneblock -e 4

# Re-enable input on all panes:
paneblock -a

# Disable input on all panes EXCEPT 0,4,6:
paneblock -id 0 4 6
```

##### Groups
`paneblock [-g|o|e|d|+] <group_name> [pane_index(es)]`
Panes can be grouped by name and enabled/disabled the same as individual panes.
Examples:

```
# Create a group named 'groupA' and add panes 0,2,3 to it
paneblock -g groupA 0 2 3

# Append pane(s) to an existing group
paneblock -g groupA + 6 7

# Enable panes in specified group
paneblock -eg groupA

# Disable panes in specified group
paneblock -dg groupA

# Enable only panes in specified group (disable all other panes/groups)
paneblock -og groupA
```





