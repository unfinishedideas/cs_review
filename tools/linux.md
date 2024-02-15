# Linux Cheat Sheet

| command     | action | example |
| ----------- | ------ | ------- |
| man         | See the manual page for any of these commands for a more detailed explanation plus extra options (which they pretty much all have) |  `man ls` |
| scp         | Copy a file from one machine to another using ssh like protocol | `scp /path/to/file username@a:/path/to/destination` |
| ssh         | Login with an ssh to another machine | `ssh username@hostname` |
| sed         | Search and replace inside a file (dangerous but useful!) |  `sed -i '' 's/#Text To Replace/Text To Replace With/g' /etc/ssh/sshd_config` |
| whoami      | See which user you are in the shell | `whoami` |
| grep        | Search an output (or file) for a particular phrase. Grep is really powerful, combine with pipes** and stuff | `grep "string" /path/to/file` |
| head / tail | Look at the first or last few lines of a file | `head file.txt` `tail file.txt` |
| diff        | Compare two files, line by line and output the difference | `diff file1 file2` |
| cmp         | Compare two files, byte by byte | `cmp file1 file2` |
| ps          | Show the currently running system processes | `ps` |
| kill        | Kill a process by it's pid | `kill 12345` |
| chmod       | Change file permissions for different groups. See the man page for different number permission codes. Each number represents different users the order is: owner, group, others | `chmod 777 ./filename` |
| chown       | Change the owner of a file | `chown new_owner file` |
| ifconfig / ipconfig    | Get network information about the system ip address, adaptors etc | `ifconfig` |
| wget        | Download content from webservers | `wget https://wordpress.org/latest.zip` |
| passwd      | Change a user's password (useful for creating a password for root user when one is not created) | `passwd` |
| sudo        | Super user do! Enables users to run programs with security privledges of another user, usually root. | `sudo whatever_command_you_want` |
| su          | command to switch the current user | `su root` |
| alias       | Create a customized shortcut for a command or series of commands | `alias update='sudo apt-get update && sudo apt-get upgrade -y && sudo snap refresh'` |
| whereis     | Locate a file / folder in the file system | `whereis passwd` |
| whatis      | Get a one page manual description of a command | `whatis chmod` |
| top         | Provide a real-time dynamic view of the system resources being used | `top` |
| >           | Output the result of a command to a file (overwrites if the file exists!) | `./command > new_file` |
| >>          | Append the result of a command to a file | `./command >> file_that_already_exists` |
| pipe**      | Run Output the result of a command to another program. See note below by the ** | `./program1 pipe** ./program2` |
| &           | Run the process in the background (use `ps` and `kill` to stop it) | `./some_program &` |
| nohup       | Run a script in the background that won't get canceled by SIGHUP signal. Bonus add `disown` as well to remove from the job list of the current shell
| cd          | change the current working directory | `cd ./new_directory` or absolute path `cd /usr/usrname/home` |
| mv          | Move or rename a file | `mv ./og_file.txt ./new_place/renamed_and_moved_file.txt` |
| ls          | List the contents of a directory (adding `-la` is also useful) | `ls -la` |
| cp          | Copy a file or directory (use `-r` for recursive copy) | `cp ./file ./file_copy` or `cp -r ./dir ./new_dir_with_sub_dirs` |
| rm          | Remove a file (use -d to destroy a directory) | `rm file` or `rm -d folder` |

** markdown wont let me write | (pipe) inside a table. Replace every pipe** with |

## Links

[Tmux - incredibly useful shell extension](https://linuxhandbook.com/tmux/)
[Linux Command Org](http://linuxcommand.org/tlcl.php)

## Tmux Stuff

| Command | Explanation |
| ------- | ----------- |
| `tmux` | start a new session |
| `tmux new -s name` | start a new session with a name |
| `tmux ls` | List all tmux sessions |
| `tmux kill-session -t name` | kill the named session |
| `tmux kill-session -a` | kill all but the last used session |
| `tmux kill-server` | kill all tmux sessions |
| `tmux attach -t name` | attach/enter the named session |
| `[Ctrl+b] + d` | Detach/exit the current session |
| `[Ctrl+b] + $` | Name or rename the current session |
| `[Ctrl+b] + c` | Create a new window |
| `[Ctrl+b] + ,` | Name or rename the current window |
| `[Ctrl+b] + w` | List all windows |
| `[Ctrl+b] + &` | Kill the current window |
| `[Ctrl+b] + n/p/N` | Move to next/previous or Nth window |
| `[Ctrl+b] + %` | Create a horizontal pane |
| `[Ctrl+b] + “` | Create a vertical pane |
| `[Ctrl+b] + space` | Toggle layout of the current pane |
| `[Ctrl+b] + z` | Zoom into the current pane |
| `[Ctrl+b] + x` | Kill the current pane |
