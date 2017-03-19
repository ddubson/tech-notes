# File and Directory Permissions

## Hard and Soft Links

* `symlink` -&gt; symbolic link
* `ln -s [target] [link]` -&gt; -s = symbolic
* If the source is removed or deleted, the symlink is broken
* `hardlink` -&gt; can’t link across FS, linking to a specific inode on the FS
* `ln [target] [link]`
* Hard links  permissions are uniform, one link has the same permissions as another link to the same node

## Permissions

* \[x\]\[yyy\]\[zzz\]\[ccc\] \[inode-links\]\[owner\]\[group\]
* `d` -&gt; directory
* `-` -&gt; file
* Whenever permissions are set, bits are set.
* first three -&gt; owner of file
* second three -&gt; group of file
* third three -&gt; everybody
* `r` -&gt; read, `w` -&gt; write, `x` -&gt; execute
* When a `user` creates a file, the file inherits the group of that user, \`user\`
* \`umask\` -&gt; settings of a mask that controls how file permissions are set for newly created files
* `chmod` 
  * u-w = user, remove write
  * u+w = user, add write
  * g+w = group, add write
  * o+w = other users, add write
  * a+r = all, add read
* To navigate into a directory, you must have execute permissions \(not read permissions\)
* \`usermod -G \[group\] \[user\]\` -&gt; add user to group
* \`-X\` -&gt; execute permissions should be set on directories, not files
  * \`chmod uw+X -R dir/\`
* Octal Notation
  * 4 = read
  * 2 = write
  * 1 = execute
* setuid - sticky-bit -&gt; execute as another user if set \(\`-T\`\)
* setgid - execute file as permissions of group, not of running user
  * \`chmod u+s test\`

## umask

* default permissions that are set when creating a file or directory for a user.
* Files start at 666
* Directories start at 777
* e.g. 
  * 0
  * 0 -&gt; no masking, 6 = raw
  * 2 -&gt; write is masked, 4 = read
  * 2 -&gt; write is masked, 4 = read
* Setting a temporary umask: \`umask \[octal\]\`
* Set permanent umask: \`/etc/bashrc\` -&gt; find \`umask\` parameter and change



