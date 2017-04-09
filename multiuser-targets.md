# Switching User Targets

* get default target -&gt; `systemctl get-default`

## Shells

Interactive Shell \(requires input at the terminal\)

```
.bashrc -> executed in an interactive shell

.bash_profile -> executed in login shell

/etc/profile -> executed whenever any user logs in to the system.
```

Login Shell

`su` - -&gt; login shell

`su --login` -&gt; login shell

## Targets

	1. multi-user.target

	2. graphical.target

	3. emergency.target &lt;- root mode

	4. rescue.target - single user env, min requirements loaded



Available targets installed

```
systemctl -t help
systemctl list-dependencies multi-user.target
systemctl get-default
```

/Targets are grouping of services+config files/



Allows switching between targets…

```
systemctl isolate multi-user.target
systemctl get-default
```

Set default target

	`systemctl set-default multi-user.target`

Sets default.target which is a symlink



At system launch, edit grub menu option for primary boot and edit the following line with tail end option of targets:![](/assets/rhel-targets-1.png)

