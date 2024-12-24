# Dual Booting Instructions


# How to Dual Boot Windows and Linux (Ubuntu)

Dual-booting allows you to use both Windows and Linux on the same computer. Here's how to set it up.

---

## **1. Prepare Your System**

1. **Backup Your Data**:  
   Before making any changes, back up important files. Although dual booting is safe, it's better to be cautious.

2. **Check System Requirements**:  
   Ensure your computer has at least:
   - 50 GB of free disk space.
   - A working USB port or DVD drive.

3. **Download Ubuntu**:  
   - Go to the [official Ubuntu website](https://releases.ubuntu.com/focal/). 
   - Note that we are installing Ubuntu Focal - 20.04 and not the latest version 24.04. This is because ROS-1 is compatible only with Ubuntu 20.04 as of now, so please don't install Ubuntu 24.04.

4. **Create a Bootable USB or DVD**:  
   - Download a tool like [Rufus](https://rufus.ie) (for USB) or use a DVD-burning program.  
   - Insert a USB drive (at least 8 GB). Ensure that nothing important is there in this USB drive because it needs to be formatted before installing.   
   - Open Rufus, select the downloaded Ubuntu file (ISO), and create a bootable USB.

---

## **2. Prepare Windows**

1. **Disable Fast Startup**:  
   - Open the Windows Start Menu, search for "Power Options," and open it.  
   - Click "Choose what the power buttons do" > "Change settings that are currently unavailable."  
   - Uncheck "Turn on fast startup," and save.

2. **Disable Secure Boot (if needed)**:  
   - Restart your computer and enter the BIOS/UEFI settings (usually by pressing a key like `F2`, `F12`, `DEL`, or `ESC` during startup).  
   - Look for "Secure Boot" in the settings and disable it. Save and exit.

3. **Create Free Space for Linux**:  
   - Right-click on the Start button, select "Disk Management."  
   - Right-click a partition (usually your C: drive), select "Shrink Volume."  
   - Allocate at least 50 GB for Linux. Leave the space **unallocated** (don’t format it).

---

## **3. Boot into Ubuntu Installer**

1. **Insert the Bootable USB/DVD**:  
   Plug in the USB or insert the DVD you created earlier.

2. **Restart and Boot from USB/DVD**:  
   - Restart the computer and enter the boot menu (usually by pressing `F12`, `ESC`, or `F9`).  
   - Select the USB/DVD to boot from.

3. **Try Ubuntu or Install Ubuntu**:  
   When Ubuntu boots, you'll see two options:
   - **Try Ubuntu**: Explore Ubuntu without installing.  
   - **Install Ubuntu**: Start the installation process.

   Choose **Install Ubuntu**.

---

## **4. Install Ubuntu**

1. **Choose Installation Language**:  
   Select your language and click "Continue."

2. **Prepare for Installation**:  
   - Check "Download updates while installing Ubuntu" (optional but recommended).  
   - Check "Install third-party software" for Wi-Fi and media support.  
   - Click "Continue."

3. **Select Installation Type**:  
   Choose **"Install Ubuntu alongside Windows Boot Manager."**  
   - If this option isn't available, select "Something Else" and manually partition the unallocated space.  
   - For manual partitioning:
     - Create a **Root partition** (`/`) of at least 15 GB (ext4 format).
     - Optionally, create a **Home partition** (`/home`) for personal files.
     - Create a **Swap partition** (equal to your RAM size, up to 8 GB).

4. **Select Your Location**:  
   Choose your time zone and click "Continue."

5. **Create a User Account**:  
   - Enter your name, a username, and a password.  
   - Remember this password, as you'll need it often.

6. **Begin Installation**:  
   - Click "Install Now."  
   - Review the changes and confirm when prompted.  
   - Wait while Ubuntu installs.

---

## **5. Configure Boot Options**

1. **Restart After Installation**:  
   - Remove the USB/DVD when prompted, and press "Enter" to restart.

2. **GRUB Bootloader**:  
   When the computer restarts, you'll see the GRUB menu. This allows you to choose between:
   - **Ubuntu**: Boots into Linux.
   - **Windows Boot Manager**: Boots into Windows.

---

## **6. Post-Installation Steps**

1. **Update Ubuntu**:  
   - Open a terminal (Ctrl+Alt+T).  
   - Run:  
     ```
     sudo apt update && sudo apt upgrade
     ```

2. **Access Files from Windows**:  
   Your Windows files will be accessible from Ubuntu under "Other Locations" in the File Manager.

---

## **Tips and Troubleshooting**

1. **Can’t See GRUB Menu?**  
   - Restart your computer and press `Shift` or `ESC` repeatedly during startup.  
   - If GRUB still doesn’t show, you may need to repair it using a live USB.

2. **Need More Disk Space for Ubuntu?**  
   You can shrink the Windows partition further using Disk Management.

3. **Switching Between Systems**:  
   Restart your computer and select the desired OS from the GRUB menu.

---

Enjoy your journey into Linux!
