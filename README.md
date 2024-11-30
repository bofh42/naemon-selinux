# naemon-selinux
SELinux policies for Naemon.

# Description
SELinux policies written for Naemon. Policies are additional to the naemon part in [Fedora selinux-policy](https://github.com/fedora-selinux/selinux-policy).  
This is far from beeing perfect, but i want to try and run Naemon in enforcing mode on RHEL 9.  
Big parts are copied from the nagios.te in [Fedora selinux-policy](https://github.com/fedora-selinux/selinux-policy) and the rest collected from audit2allow.

## Dependencies
selinux-policy-devel

## Installation
* clone the repository
* `make -f /usr/share/selinux/devel/Makefile`
* `semodule -i naemon_42.pp`
* `restorecon restorecon -Rv /etc/naemon /var/log/naemon /var/cache/naemon /var/lib/naemon`
