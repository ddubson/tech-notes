# Create Partition from Free Space

#### Step by Step

1. `fdisk /dev/hda`

2. type p \(it will print partition table\) 

3. type n \(for creating a new partition\) 

4. press enter \(it will take the default value\) 

5. Press enter \(it will take last cylinder as default value\) 

6. Press p \(it will print the new partition table , can u see `/dev/hda8 Linux`\)

7. Press w \(to save\) after that to activate the partition without rebooting 

type the command `partprobe` 

1. `mkfs -t ext3 /dev/hda8` \( make it as a ext3 filesystem\) 

2. `mkdir /test` 

3. `mount /dev/hda8 /test` \(to mount the partition\) 

http://linux.ittoolbox.com/groups/technical-functional/redhat-l/create-a-partition-from-a-free-space-unpartitioned-1048337

