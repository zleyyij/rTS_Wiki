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

    > If you are not using external media you may need to SKIP this step. Mount the internal disk to `/home/partimag` and Clonezilla will write to it.

3. Choose "Beginner"

    ![clonezilla-level](/assets/clonezilla/clonezilla-level.png)

4. Choose "savedisk", if you want to image specific partitions that is outside the scope of this guide.

    ![clonezilla-level](/assets/clonezilla/clonezilla-save-type.png)

5. Provide a file name for your image

    ![clonezilla-level](/assets/clonezilla/clonezilla-name.png)

6. Choose which disks you want to take an image of

    > Identify your disk based on size and possibly by label.

    ![clonezilla-level](/assets/clonezilla/clonezilla-disk-sel.png)

7. The default compression method should be fine.

    ![clonezilla-level](/assets/clonezilla/clonezilla-compression.png)

8. In most cases you should skip the disk check and use the default option that Clonezilla provides.

    ![clonezilla-level](/assets/clonezilla/clonezilla-fs-check.png)

9. Checking the image was successful is the default and encouraged. Disable it if you want to save time.

    ![clonezilla-level](/assets/clonezilla/clonezilla-integrity.png)

10. Encrypting the image is not withing the scope of this guide but is possible.

    ![clonezilla-level](/assets/clonezilla/clonezilla-encryption.png)

11. Leaving the default for the final action will allow you to see the results, and continue without needlessly.

    ![clonezilla-level](/assets/clonezilla/clonezilla-reboot.png)

12. You will see a summary of the command that will be run. Press "enter" to continue.

    ![clonezilla-level](/assets/clonezilla/clonezilla-confirmation.png)
