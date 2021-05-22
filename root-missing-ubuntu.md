## Root missing in Ubuntu?

In Ubuntu, a new user might find that the root account is missing.

You wouldn't see a root option with GNOME's login menu. Nor would it let you log in as root by typing
```sh
$su root
```
in shell.

This is because, the Root account password is locked in Ubuntu.
To set/reset password for root. Use the command,
```sh
$sudo passwd root
```

If you want to disable root account, you need to lock the root account by using the command
```sh
$sudo passwd -l root
```

### sudo
Ubuntu advices users to avoid using root. Instead, it uses a program called sudo. The offical definition of sudo goes like this,
Sudo (su "do") allows a system administrator to delegate authority to give certain users (or groups of users) the ability to run some (or all) commands as root or another user while providing an audit trail of the commands and their arguments.

To add a user as a sudo user (a "sudoer"), the visudo command must be run as root.
By default, the visudo command uses the editor vi. You may set the EDITOR environment variable to the editor of your choice, such as in this example with the editor "nano":
`# EDITOR=nano visudo`

visudo opens the file /etc/sudoers. To add a user or group to the sudoers list, enter the below line into the file.
```sh
%john ALL=(ALL) ALL
```

The sudo main page is [sudo](http://www.gratisoft.us/sudo)

Benefits of using sudo are explained here [RootSudo](https://help.ubuntu.com/community/RootSudo)

To continue to SUDO configuration : [SUDO tutorial]((https://notes-from-a-dev.blogspot.com/2011/06/sudo-tutorial.html))
To read more about creating and managing users and groups: [Users and Groups]((https://notes-from-a-dev.blogspot.com/2011/06/users-and-groups.html))