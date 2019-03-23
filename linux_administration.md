# Managing GIT Repository

## For managing the GIT repository, following step need to be done.
 Go to Documentation folder which resides in /infrx_admin/documentation

-Adding User Information
  1. git config --global user.email "user email id"
  1. git config --global user.name "Name of the user"

- For adding a new file: 
  1. vim filename.md
  1. git add filename
  1. git status filename
  1. git commit filename
  1. git status filename
  1. git push

- To edit the already saved file:
  1. Find the desired document in Documents folder.
  1. vim filename
  1. Make the changes according to the users needs.
  1. git commit filename
  1. git status filename
  1. git push

- To push a file on teams.
  1. Make sure you have done git commit filename
  1. And then do git push

- To know the status of the file
  1. Use the command git status filename

- To pull a file.
  1. Use the command  git pull 

# Extending volume in LVM

##  Scenario: Having 50 GB in ‘/’ partition and almost full, need to reduce space from ‘/home’  and extend that space with ‘/’.

- Check our disk partitions and mounts   ``` df -Th ```
- First need to reduce the /home partition 
  
  1.  Check ‘/home’ directory and confirm all the directory.
  1. Check “passwd” file to make sure any local users are there  ``` vim /etc/passwd ```
  1. Unmount all the network shares.
- Reducing /home mount.
  1. Unmount ‘/home’    ``` umount /home ```
  1. Check free space in Volume group (vg)     ``` vgs ```
  1. Reduce LV, (for lv name use lvdisplay command)  ``` lvreduce -L 50G /dev/rhel/home ```
  1. Now check vg space   ``` vgs ```
  1. Format the reduced partition  ``` mkfs.xfs -f /dev/rhel/home ```
  1. Mount ‘/home’  ``` mount /home ```
  1. To mount network shares NCIWIN directory should be there inside ‘/home’ create one  ``` mkdir /home/NCIWIN ```
  1. Again, mount the network shares  ``` mount -a ```
  1. Check /home/NCIWIN whether shares loaded or not.

- Now check the mounts, we can see ‘/home’ reduced to 50GB.   ``` df -Th ```
- Extending ‘/’.

  1. Confirm which LV want to extend  ``` lvdisplay ```
  1. Look for the mount lv path  	``` lvextend -L +91G /dev/rhel/root ```
  1. To make the change give  ``` xfs_growfs /dev/rhel/root ```
  1. Check the remaining vg space  ``` vgs ```
  1. Confirm all mounts  ``` df -Th ```

- After extending.

  1. Stop rstudio server  ``` rstudio-server stop ```
  1. Unmount all shares  ``` umount -l /home/NCIWIN (use ‘l’ for force unmount) ```
  1. Reboot the server  reboot
- After reboot.
  1. Check all network mounts. ``` df -Th ```
  1. Start rstudio   ``` rstudio-server restart ```

