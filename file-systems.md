# Linux File Systems

* Data is stored on the storage device in a certain manner
  * Organized, easily located
  * Persistent
  * Integrity is preserved
  * Quickly retrieved at a later time.
* Disk file system is a generic implementation of a greater file system concept
* Filesystem Hierarchy Standard \(FHS\)
* Linux file system uses a hierarchy structure to organize data
* Linux systems have a standard in which root directory has several of the same sub directories in a certain order or fashion



	• \`/etc\` contains text-based configuration files used by the system as well as services running 

	on the system. We can edit these files with a text editor and then customize how Linux 

	behaves in different manners. 

		\* \`/etc/aliases\`- Contains a table used to redirect all to local users 

		\* \`/etc/exports\` -Configured file systems to be exported to remove NFS clients 

		○ \`/etc/fstab\` - lists the partitions and file systems that will be automatically mounted when we boot our Linux system 

		○ \`/etc/ftpusers\` - Controls users access to FTP service running on a Linux system 

		○ \`/etc/group\` - Contains local group definitions 

		○ \`/etc/grub.conf\`  - Contains configuration parameters for the init process 

		○ \`/etc/hosts\` - This contains a list of hostname to IP address mappings that we 

	can use to resolve certain hostnames 

		○ \`/etc/inittab\` - Contains configuration parameters for the init process

		○ \`/etc/init.d\` - This is a sub directory that contains startup scripts and services 

		○ \`/etc/rc.d/init.d/\` - Red Hat or CentOS based systems startup scripts

		○ \`/etc/passwd\` - This is our Linux systems users accounts file

		○ \`/etc/shadow\` - This contains encrypted passwords for our user accounts

		○ \`/etc/resolv.conf\` - This is where we specify what DNS server and domain suffix that our 

	system is going to use

		○ \`/etc/X11\` - Has the X windows configuration files 

# Disk Filesystems

* `ext2` - second extended file system \(1993\)

* `ext3` - updated version of ext 2; third extended file system; offers journaling - records transactions to a journal-transaction based actions
* `Reiser` - utilizes journaling; allows for larger files \(8TB\); performs faster than ext2; ext3
* `ext4` - fourth extended file system; supports volumes of 4 exabytes



