---
layout: default
title: Using Clonezilla
nav_exclude: false
has_children: false
parent: Disks
search_exclude: false
last_modified_date: 2022-08-07
---

# Using Clonezilla

This article relies on the live media [created here](/docs/live-sessions/linux-live-session)

## Launching Clonezilla
In the Linux Live Session open a Terminal from the menu and run `sudo clonezilla`.

![clonezilla-main](/assets/clonezilla/clonezilla-main.png)

## Creating a disk image
These steps are for writing to a local device, the tool can also be used for writing to remote servers via SSH/SMB/NFS etc.

1. Choose "device-image"
2. Choose "local_dev"

    > You are now prompted to insert any media that you want to store the image on.

    ![clonezilla-local-dev](/assets/clonezilla/clonezilla-local-dev.png)

3. Clonezilla enumerates all available devices then asks where to store the image we are making.

    > Select the location to STORE the image. Not the disk that we are making an image of.

    ![clonezilla-local-dev](/assets/clonezilla/clonezilla-storage-sel.png)

4. You are asked where to store the image on the chosen disk. You can navigate the file structure by pressing "Enter" on any folder. When you have the correct destination selected, cycle to "Done" to continue.

    ![clonezilla-folder0](/assets/clonezilla/clonezilla-folder0.png)
    ![clonezilla-folder1](/assets/clonezilla/clonezilla-folder1.png)

    > If you do not have a folder created you can create one in another terminal with the command `sudo mkdir /tmp/ocsroot_bind_root/Image_Destination`
    > 
    > Refresh the view of the disk with the "Browse" option.

5. Choose "Beginner"

    ![clonezilla-level](/assets/clonezilla/clonezilla-level.png)

6. Choose "savedisk", if you want to image specific partitions that is outside the scope of this guide.

    ![clonezilla-level](/assets/clonezilla/clonezilla-save-type.png)

7. Provide a file name for your image

    ![clonezilla-name](/assets/clonezilla/clonezilla-name.png)

8. Choose which disks you want to take an image of

    > Identify your disk based on size and possibly by label.

    ![clonezilla-disk-sel](/assets/clonezilla/clonezilla-disk-sel.png)

9. The default compression method should be fine.

    ![clonezilla-compression](/assets/clonezilla/clonezilla-compression.png)

10. In most cases you should skip the disk check and use the default option that Clonezilla provides.

    ![clonezilla-fs-check](/assets/clonezilla/clonezilla-fs-check.png)

11. Checking the image was successful is the default and encouraged. Disable it if you want to save time.

    ![clonezilla-integrity](/assets/clonezilla/clonezilla-integrity.png)

12. Encrypting the image is not withing the scope of this guide but is possible.

    ![clonezilla-encryption](/assets/clonezilla/clonezilla-encryption.png)

13. Leaving the default for the final action will allow you to see the results, and continue without needlessly.

    ![clonezilla-reboot](/assets/clonezilla/clonezilla-reboot.png)

14. You will see a summary of the command that will be run. Press "enter" to continue.

    ![clonezilla-confirmation](/assets/clonezilla/clonezilla-confirmation.png)

15. The last step before writing our image is the summary page. We assume everything is correct and type "y" then hit "enter".

    ![clonezilla-summary](/assets/clonezilla/clonezilla-summary.png)

16. When it is done you will be left with a success message, press "enter" to finish and fall back to a commandline.

    ![clonezilla-finished](/assets/clonezilla/clonezilla-finished.png)

## Mounting a Clonezilla image

