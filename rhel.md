# Common Commands

### Reboot / Shutdown / Init commands

* Systemd has replaced run levels
* Deprecated way of controlling the system:
  * Shutdown systems \(runlevel 0\) -- `init 0`
* Restart system \(runlevel 6\) -- `init 6`

##### Restart system

```
reboot
systemctl reboot
shutdown -r [time in mins] [message]
```

uses wall command

e.g. shutdown at midnight -- `shutdown -r 00:00`

##### Cancel shutdown command

`shutdown -c`

##### Power off / Shutdown \(halt = poweroff\)

```
halt
systemctl halt
shutdown -h [Time] [Message]
init 0
systemctl poweroff
shutdown -p
```

* Available targets: /usr/lib/systemd/system/\*

* **systemd** manages everything, replaced sysvinit

* allows to boot multiple services simultaneously.

##### Available targets installed

```
systemctl -t help
systemctl list-dependencies multi-user.target
systemctl get-default
```

---



