# CPU and Memory

## pgrep

* `ps` : list processes on system
* `pgrep` : ps + grep utilities combined
  * e.g. `pgrep gnome -l` : view all processes related to gnome
  * e.g. `pgrep httpd -l`
* `pgrep -u [user] -l [grep-pattern]` : list all processes that a certain user is running
* `pgrep -v -u [user] -l` : list all processes NOT running by root

## pkill

* Kill processes with the help of naming semantics
* `pkill [name-of-process]` -&gt; kill process by name
  * `pkill httpd` -&gt; sends -15 signal by default
  * `pkill -9` -&gt; kill process immediately \(9=SIGKILL\)
  * `kill -l` -&gt; list all signals
  * `pkill -t pts/1` -&gt; kill all processes of another user with TTY of pts/1
* Common Signals:

| Signal Code | Signal Number | Description |
| :--- | :--- | :--- |
| SIGHUP | 1 | Report termination of process |
| SIGINT | 2 | Keyboard interrupt |
| SIGQUIT | 3 | Exit process |
| SIGKILL | 9 | Kill process with no interruptions |
| SIGTERM | 15 | Terminate process cleanly |
| SIGCONT | 18 | Continue process after stop |
| SIGSTOP | 19 | Stop so you can start later |
| SIGSTP | 20 | Stop process but can be ignored |

[https://i.stack.imgur.com/9EQBC.png](https://i.stack.imgur.com/9EQBC.png)

---

## Process Manipulation

* `&` -&gt; background process
* `jobs` -&gt; background jobs
* `kill -SIGSTOP %[job-number]` -&gt; stop job \(not kill\)
* `kill -SIGCONT %[job-number]` -&gt; continue job that was stopped
* `ps` -&gt; running processes
* `ps -u [user]` -&gt; running processes of a user

### Priority to process

Suggest priority of the process to the kernel.

Set the `niceness` of the process

-20 -&gt; most favorable

19 -&gt; least favorable

```
nice -n 0 httpd                  # give priorit level of 0 to httpd
ps aux
ps -axo pid,comm,nice            # get pid, command name, and priority level of all processes
renice -n 10 [pid]               # renice a process
renice -n 10 ${pgrep httpd}      # renice all httpds (via invoking a subshell)
```

### System load averages

* `w` -&gt; users online, load averages
* `uptime`
* Load average is the percent of the processor usage
* `cat /proc/cpuinfo`-&gt; identify number of processors
* Load average = \(\(load\) / \# of processors\) \* 100 \( e.g. \(0.53 / 2\) \* 100 = load on the cpu\)
