---
title: Prepare with Ventoy
layout: default
nav_order: 2
parent: Preparing the ISO
permalink: /preparing-the-iso/with-ventoy/
---

# Prepare with Ventoy

You have probably downloaded the Windows 11 IoT Enterprise 2024 x64 version I talked about before. Here, we will be preparing an USB Flash Drive with that ISO using Ventoy and AnyBurn.

## Download and Install Ventoy

Unlike tools like Rufus where you have to process and prepare your USB Flash Drive every time you want to boot or install from an ISO, Ventoy allows you to prepare your flash drive once and just boot any ISO you want from that. It also lets you keep multiple ISO files in the same flash drive, which is probably the biggest selling point (even though it's free 😉).

{: .link-title }
> Open Link
> 
> [https://www.ventoy.net/en/download.html](https://www.ventoy.net/en/download.html)

Once the link opens, click on one of the available download links. They all lead you to sourceforge, so it doesn't really matter. But you can click the one for Windows if you're feeling sane.

![Downloading Ventoy (1)](../../images/1-2-download-ventoy-1.png)

Why didn't I just give you the sourceforge link directly? Well, I don't want to have to update this guide every time they release a new version. So I'm showing you the regular process, not the spoonfed process. But now that you're here, download the **zip** that's marked for Windows.

![Downloading Ventoy (2)](../../images/1-2-download-ventoy-2.png)

Congrats! Now you have Ventoy. We still have to install it though.

For that, you should first extract that **zip** you just downloaded. I'm choosing not to include screenshots for that, because if you don't know how to extract a zip, you should probably not be reinstalling Windows on your own. Once you have extracted it, run **"Ventoy2Disk.exe"** to start the process.

Installing Ventoy is really easy. Just make sure the correct USB Flash Drive is selected (1) and then click Install (2).

![Install Ventoy)](../../images/1-2-ventoy-install.png)

Ventoy generally warns you about wiping your flash drive twice. That should give you a clue that you probably shouldn't keep anything important in the flash drive before continuing with this process.

![Confirm Wipe with Ventoy)](../../images/1-2-ventoy-confirm-wipe.png)

Once the process ends, it'll pop up with a Congratulations dialogue. At this point, just click Okay and exit the program.

![Ventoy Complete](../../images/1-2-ventoy-done.png)

So, now we have Ventoy. The best part about choosing Ventoy over Rufus? You can continue to use this flash drive casually. No need to format it first. Ventoy doesn't bite.

## Download and Install AnyBurn

Ventoy is a rather convenient tool if you can keep a flash drive preinstalled with it. But it doesn't allow you to make changes to the ISO as Rufus offers. Since we need those changes, we will be modifying the ISO a little bit with AnyBurn.

This is completely unnecessary if you don't want to make changes to the ISO. So for Linux enthusiasts and Windows bloatware enjoyers, Ventoy is just as good as Rufus with only upsides and no downsides.

The free version of AnyBurn is good enough for our needs. A more powerful alternative for the same task is PowerISO (suppose the name didn't give it away). But I don't want to get into pirated programs at this stage of the guide, so we'll go with AnyBurn.

{: .download-title }
> Download File
> 
> [https://www.anyburn.com/anyburn_setup.exe](https://www.anyburn.com/anyburn_setup.exe)

This program is also available via WinGet, so if you'd rather use that, you may.

{: .cmd-title }
> Run in CMD
> 
> winget install PowerSoftware.AnyBurn

Just download and install the program as you do with any other program on Windows. It simply involves clicking a few buttons before you're done, so I didn't bother to screenshot the process.

## Modify the ISO

I've made a backup of the changes that Rufus makes to the ISO. If you want to look at the specific changes that I asked Rufus to make, you can do that by [opening this link](../with-rufus/).

{: .download-title }
> Download File
> 
> [https://naeembolchhi.github.io/guide-windows-11-clean-install/resources/unattend-script.zip](https://naeembolchhi.github.io/guide-windows-11-clean-install/resources/unattend-script.zip)

Once you download the backup, go ahead and extract the files inside with all folders intact.

The script does several things for us, including the automatic creation of a local user with the username of **NaeemBolchhi**. Since you're not creepy at all and you want to use your own username instead of masquerading as me, let's change the username.

Open the folder that you extracted, and the every other folder inside, until you find an **xml** file.

![Open Folder for Unattend Script](../../1-2-script-open-folder.png)

Now edit this file with Notepad, Notepad++, or NotepadNext. Any editing tool that can do Find-and-Replace will do.

![Edit Unattend Script with Notepad](../../1-2-script-edit-notepad.png)

Type **NaeemBolchhi** in the first box (1), and your custom username in the second box (2). It's probably better not to have spaces in your username as that makes a lot of filepaths simpler to write.

If there's a **Replace All** button (3), click that. If your editor doesn't have that, click **Replace** multiple times.

![Replace Username in Unattend Script](../../1-2-script-replace-username.png)

Confirm that your username has appeared in multiple places within the file. Then save and exit.

Now that our changes are ready, we can put this file inside the ISO.

ISOs are special, and if you modify these with regular archiving tools, you might ruin their bootability. That's why we're using AnyBurn.

Start AnyBurn that you previously installed and click "Edit image file".

![AnyBurn Home](../../1-2-anyburn-home.png)

Now select the unmodified ISO you previously downloaded from Massgrave (1). Once the ISO is recognized, just click **Next** (2).

![AnyBurn Select ISO](../../1-2-anyburn-select-iso.png)

Now drag and drop the **"sources"** folder you extracted a while ago into the ISO.

![AnyBurn Drag and Drop Folder](../../1-2-anyburn-add-folder.png)

If you did it right, you should get a pop-up that asks you to confirm if you want to replace the existing folder. Select **Yes to all** (1). Once that's done, click **Next** (2) for the next step.

![AnyBurn Confirm Replace](../../1-2-anyburn-confirm-replace.png)

You have to give the ISO a new name (1). It's perfectly fine to give it a completely new name instead of slightly changing it as I did. Then click **"Create Now"** (2).

![AnyBurn Rename and Save](../../1-2-anyburn-rename-save.png)

Let's wait for the process to finish.

![AnyBurn Creating New ISO](../../1-2-anyburn-creating-new-iso.png)

Once you have your ISO, we are done with AnyBurn. You can close that.

## Add the ISO to the Flash Drive

Simply copy over the modified ISO to your USB Flash Drive.

![Move the ISO to Flash Drive](../../1-2-move-iso.png)

Once that's done, we are ready to install Windows.

And remember, since you're using Ventoy, you can add multiple different ISOs to it, or simply use it like a regular flash drive.