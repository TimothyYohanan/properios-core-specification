# Properios Core Specification v2.0.0

## Section 1 - File and Directory Ownership and Permissions
#### 1.1 - The following directories must exist: '/boot', '/dev', '/etc', '/proc', '/root', '/run', '/tmp', '/usr', and '/var'.
#### 1.2 (a) - The '/boot' directory must belong to the root user, the root group, and must have 700 permissions.
#### 1.2 (b) - The '/dev' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.2 (c) - The '/etc' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.2 (d) - If the '/home' directory exists, it must belong to the root user, the root group, and must have 755 permissions.
#### 1.2 (e) - If the '/media' directory exists, it must belong to the root user, the root group, and must have 755 permissions.
#### 1.2 (f) - If the '/opt' directory exists, it must belong to the root user, the root group, and must have 755 permissions.
#### 1.2 (g) - If the '/mnt' directory exists, it must belong to the root user, the root group, and must have 755 permissions.
#### 1.2 (h) - The '/proc' directory must belong to the root user, the root group, and must have 555 permissions.
#### 1.2 (i) - The '/root' directory must belong to the root user, the root group, and must have 700 permissions.
#### 1.2 (j) - The '/run' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.2 (k) - If the '/srv' directory exists, it must belong to the root user, the root group, and must have 700 permissions.
#### 1.2 (l) - If the '/sys' directory exists, it must belong to the root user, the root group, and must have 555 permissions.
#### 1.2 (m) - The '/tmp' directory must belong to the root user, the root group, and must have 1777 permissions.
#### 1.2 (n) - The '/usr' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.2 (o) - The '/var' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.3 - In the '/usr' directory, the following directories must exist: 'bin', 'include', 'lib', 'local', 'sbin'
#### 1.4 (a) - The '/usr/bin' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.4 (b) - The '/usr/include' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.4 (c) - The '/usr/lib' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.4 (d) - If the '/usr/lib64' directory exists, it must belong to the root user, the root group, and must have 755 permissions.
#### 1.4 (e) - The '/usr/local' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.4 (f) - The '/usr/sbin' directory must belong to the root user, the root group, and must have 700 permissions.
#### 1.5 - In the '/usr/local' directory, the following directories must exist: 'bin', 'include', 'lib', 'sbin'
#### 1.6 (a) - The '/usr/local/bin' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.6 (b) - The '/usr/local/include' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.6 (c) - The '/usr/local/lib' directory must belong to the root user, the root group, and must have 755 permissions.
#### 1.6 (d) - If the '/usr/local/lib64' directory exists, it must belong to the root user, the root group, and must have 755 permissions.
#### 1.6 (e) - The '/usr/local/sbin' directory must belong to the root user, the root group, and must have 700 permissions.
#### 1.7 - Configuration files which affect the security of the system, such as firewall configuration files, must belong to the root user, the root group, and must have 600 permissions.
#### 1.8 - Files storing configurations related to the login process must belong to the root user, the root group, and must have 600 permissions.
#### 1.9 - Files pertaining to adding and/or removing Users and Groups, or changing passwords must belong to the root user, the root group, and must have 600 permissions.
#### 1.10 - Files which store Users, Groups, and Passwords must belong to the root user, the root group, and must have 600 permissions.
#### 1.11 - If the following files exist inside '/etc', they must belong to the root user, the root group, and must have 600 permissions: 'crontab', 'xattr.conf'.
#### 1.12 - If the following directories exist inside '/etc', they must belong to the root user, the root group, and must have 700 permissions: 'X11', 'apparmor.d', 'cron.d', 'cron.daily', 'cron.hourly', 'cron.monthly', 'cron.weekly', 'cron.yearly', 'dhcp', 'init.d', 'initramfs-tools', 'iproute2', 'kernel', 'modprobe.d', 'modules-load.d', 'network', 'opensc', 'rc0.d', 'rc1.d', 'rc2.d', 'rc3.d', 'rc4.d', 'rc5.d', 'rc6.d', 'rcS.d', 'selinux', 'skel', 'ssl', 'sysctl.d', 'systemd'.
#### 1.13 - If the following directories exist, they must belong to the root user, the root group, and must have 700 permissions: '/etc/ssl/private'
#### 1.14 - If the following directories exist, they must belong to the root user, the root group, and must have 755 permissions: '/etc/ssl/certs'
#### 1.15 - If the following files exist, they must belong to the root user, the root group, and must have 644 permissions: '/etc/ssl/openssl.cnf'

## Section 2 - PAM
#### 2.1 - If the default PAM configuration file exists, it must belong to the root user, the root group, and must have 600 permissions.
#### 2.2 - The directory(s) which contains PAM policies must belong to the root user, the root group, and must have 700 permissions.
#### 2.3 - The directory(s) which contains PAM module configurations must belong to the root user, the root group, and must have 700 permissions.
#### 2.4 (a) - The 'root-auth' PAM policy must exist.
#### 2.4 (b) - The 'root-auth' PAM policy must enforce that the root user is authenticated by hardware security key, and it must not affect the authentication stack when it encounters a user account that is not 'root'.
#### 2.5 (a) - The 'common-auth' PAM policy must exist.
#### 2.5 (b) - The 'common-auth' PAM policy must be used via an @include statement as the authentication stack in all PAM policies which require authentication. The only authentication modules that may be used outside of 'common-auth' and 'root-auth' are the following: pam_faildelay.so, pam_nologin.so, pam_rootok.so, and pam_shells.so.
#### 2.5 (c) - The 'common-auth' PAM policy must enforce that the root user is authenticated by hardware security key ONLY.
#### 2.6 - The PKCS-11 PAM module must exist.

## Section 3 - Commands Which Modify User Accounts
#### 3.1 (a) - All commands which can be used to create a new user account or a new group must belong to the root user, the root group, and must have 700 permissions.
#### 3.1 (b) - All commands which can be used to change the password on a user account must belong to the root user, the root group, and must have 700 permissions.

## Section 4 - Programs
#### 4.1 - The 'sudo' program is disallowed.

## Section 5 - Kernel
#### 5.1 - The kernel must be compiled with 'CONFIG_IKCONFIG=y' in order to embed the contents of the .config file used to build the kernel within the bootable kernel image [a.k.a. /boot/vmlinuz-$(uname -r)].