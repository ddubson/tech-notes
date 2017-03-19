# Logging

## journald

`journald` : logs all events on a system, accessed via journalctl, non-persistent

* `journalctl`
* logs located in `/run/log/journal` \(run directory is wiped on each boot\)
* `/etc/systemd/journald.conf` : configuration for journals
* `/etc/rsyslog.conf` : configuration of the loggers

    # last 10 lines
    journalctl -n

    #` -> explain + last 10 lines
    journalctl -xn

    # last 10 lines + listen for new messages
    journalctl -f

    # view specific units like httpd
    journalctl _SYSTEM_UNIT=[units]

## systemd-analyze

information about boot process

`systemd-analyze` or `systemd-analyze blame`

## syslogd	

• In Linux, the \*syslogd\* daemon sits in the background and receives log information from various systems and user processes.

• The location of logs in Linux \(Fedora 13\):

	○ `/var/log/` - contains logs for all common processes

Common log files of use to hackers:

* Secure \(`/var/log/secure`\) - contains information about successful and failed system logins \(username, original system used for login\). 
* Messages \(i.e. `/var/log/messages`\) - contains general messages from a variety of system components, including the kernel, specific modules, and daemons.
* Individual application logs \(i.e. `/var/log/httpd`\) - specific log files for programs.

Important Linux files:

* utmp \(`/var/run`\) - this file stores info about who is currently logged into the system \(the who command retrieves this file\).
* wtmp \(`/var/log`\) - this file records all logins and logouts to and from the system. The command last retrieves this file 



