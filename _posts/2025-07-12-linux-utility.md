---
title: "Linux Utility"
date: 2025-07-12
---

# Introduction 


The command chmod ug+x *.sh modifies file permissions for all shell script files in the current directory.
Breaking it down:

chmod - the command to change file permissions
ug+x - the permission specification:

u = user (file owner)
g = group (users in the same group as the file)
+x = add execute permission


*.sh - applies to all files ending with .sh (shell scripts)

So this command gives execute permissions to both the file owner and group members for all shell script files in the current directory. After running this command, those .sh files can be executed directly (like ./script.sh) rather than needing to call them through an interpreter (like bash script.sh).
This is commonly used when you have shell scripts that you want to make executable for yourself and others in your group.

## Example Usage

```bash
chmod ug+x *.sh
```


