# SELinux

https://wiki.centos.org/HowTos/SELinux

* Kernel-level module to enforce access permissions
* Follows the model of least privilege
* Defaults to 'enforcing' - everything is denied, series of exceptions given to individual elements of the system for them to function properly.

### Modes of operation

* **Enforcing**: the default mode which will enable and enforce the SELinux security policy on the system, denying access and logging actions
* **Permissive**: enabled but will not enforce the security policy, only warn and log actions.
* **Disabled**: SELinux is turned off

additional qualifier of 'targeted' or 'mls' which control how pervasive SELinux rules are applied, with 'targeted' being the stringent level.

`setenforce` command maybe used to toggle 'Enforcing' and 'Permissive' - changes do not persist between reboots!!

```
setenforce Permissive
setenforce Enforcing
sestatus
```

To make persistent changes, edit the 'SELINUX=' line in `/etc/selinux/config`

### Access Control

SELinux has 3 forms of access control:

* **Type Enforcement \(TE\)** - primary mechanism of access control used in the 'targeted' policy
* **Role Based Access Control \(RBAC\)** - based around SELinux users, but not used in the default 'targeted' policy
* **Multi-Level Security \(MLS\)** - not commonly used and often hidden in the default 'targeted' policy.

All processes + files have an SELinux security context

\`ls -Z\`

The output is based on 'user:role:type:mls

\`ps axZ \| grep httpd\`

### Logs

The log files are located at \`/var/log/audit/audit.log\` \(writted via auditd \(Linux Auditing System\)\)

	• If the auditd daemon is not started, the messages are written into \`/var/log/messages\`.

SELinux messages are labeled with 'AVC' keyword so they can be easily filtered.

