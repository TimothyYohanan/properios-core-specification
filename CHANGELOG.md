## v1.0.0
### Comments:
- I expect that this initial commit will be a lot to digest compared to future commits. That being said, all of the requirements listed in this version distil down to only 4 categorical requirements: adequately restrictive default file and directory permissions, adequately restrictive permissions on binaries that can create and modify user accounts and passwords, mandatory usage of a hardware security token for root user login, and prohibiting privilege escalation via the '$ sudo' command.

## v2.0.0
### Comments:
- Required 'CONFIG_IKCONFIG=y' in the kernel .config file. This setting causes the contents of the kernel .config file to be written into the bootable kernel image [a.k.a. /boot/vmlinuz-$(uname -r)] which is useful for testing subsequent changes to kernel .config settings.