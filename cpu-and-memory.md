# CPU and Memory

## pgrep

\* \`ps\` -&gt; list processes on system

\* \`pgrep\` -&gt; ps + grep utilities combined

\*\* e.g. \`pgrep gnome -l\` -&gt; view all processes related to gnome

\*\* e.g. \`pgrep httpd -l\`

\* \`pgrep -u \[user\] -l \[grep-pattern\]\` -&gt; list all processes that a certain user is running

\* \`pgrep -v -u \[user\] -l\` -&gt; list all processes NOT running by root

## pkill

\* Kill processes with the help of naming semantics

\* \`pkill \[name-of-process\]\` -&gt; kill process by name

\*\* \`pkill httpd\` -&gt; sends -15 signal by default

\*\* \`pkill -9\` -&gt; kill process immediately \(9=SIGKILL\)

\*\* \`kill -l\` -&gt; list all signals

\* 1=SIGHUP, report termination of process \(close terminal window\)

\* 2=SIGINT, keyboard interrupt

\* 3=SIGQUIT

\* 9=SIGKILL, kill process with no interruptions

\* 15=SIGTERM, terminate process cleanly

\* 18=SIGCONT, continue process after stop

\* 19=SIGSTOP, stop so you can start later

\* 20=SIGSTP, stop process but can be ignored

https://i.stack.imgur.com/9EQBC.png

\*\* \`pkill -t pts/1\` -&gt; kill all processes of another user with TTY of pts/1

---

## Process Manipulation

\* \`&\` -&gt; background process

\* \`jobs\` -&gt; background jobs

\* \`kill -SIGSTOP %\[job-number\]\` -&gt; stop job \(not kill\)

\* \`kill -SIGCONT %\[job-number\]\` -&gt; continue job that was stopped

\* \`ps\` -&gt; running processes

\* \`ps -u \[user\]\` -&gt; running processes of a user



### Priority to process

Suggest priority of the process to the kernel.

Set the \`niceness\` of the process

\*-20\* -&gt; most favorable

\*19\* -&gt; least favorable



\`nice -n 0 httpd\` -&gt; give priorit level of 0 to httpd

\`ps aux\`

\`ps -axo pid,comm,nice\` -&gt; get pid, command name, and priority level of all processes

\`renice -n 10 \[pid\]\` -&gt; renice a process

\`renice -n 10 ${pgrep httpd}\` -&gt; renice all httpds \(via invoking a subshell\)



### System load averages

\* \`w\` -&gt; users online, load averages

\* \`uptime\`

\* Load average is the percent of the processor usage

\* \`cat /proc/cpuinfo\` -&gt; identify number of processors

\* Load average = \(\(load\) / \# of processors\) \* 100 \( e.g. \(0.53 / 2\) \* 100 = load on the cpu\)



