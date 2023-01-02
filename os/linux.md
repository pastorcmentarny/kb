# LINUX COMMANDS
### List of commands to perform useful things that I keep forgetting how to do it.

* ``` find . -print | grep '.*ufo*'``` - Find all files in current folder that contains ufo in their name
* ``` diff -rq folder1 folder2``` - Compare difference between 2 folders (in this case in current folder)
* ``` tail -n 10 warnings.log``` - Display last 10 lines from file warnings.log
* ``` tail -f /dev/null | nc -l 192.168.0.201 30003 >> /home/pi/data/aircrafts.txt``` - to use to collect data from port stream. `tail -f /dev/null` is a empty input 
* ``` sudo mount -t auto -v /dev/mmcblk0p3 /mnt/data``` - mount external drive
* ``` sudo umount /dev/sda2``` - unmount external drive
* ``` sudo mv -v /mnt/data/photos/2019/11/05/ /mnt/data/photos/2019/11/06/ /mnt/data/photos/2019/11/07/ /mnt/data/2019/11/08/   /mnt/backup/cctv/2019/11/``` - move multiple folders into selected folder 
* ``` pip3 list``` - display list of installed packages in python 3
* ``` sudo lsblk -o UUID,NAME,FSTYPE,SIZE,MOUNTPOINT,LABEL,MODEL``` - display data about mounted devices.
* ```  ps -ax | grep "python" ``` find specific process name in running
* ``` sl``` - stream train animation :D
* ``` cloc``` - counting line 
* ```cat /etc/os-release```  - to check what OS you are running
*  `history > commands_history.txt` - save history of commands to file
