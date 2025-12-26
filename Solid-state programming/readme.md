### Method for SSD Flashing and Booting

#### 1.Install the balenaEtcher software

Click balenaEtcher-2.1.4.Setup.exe to start the installation, then launch the software after installation.

<img width="554" height="352" alt="image" src="https://github.com/user-attachments/assets/089ad90e-2f86-4692-ac23-a14f3de0790d" />

#### 2. Insert the solid-state drive (SSD)

Required tool: SSD flasher enclosure (not provided separately, please prepare it yourself).

<img width="510" height="199" alt="image" src="https://github.com/user-attachments/assets/50d81a9b-9ff4-4baa-9017-4f4d332f063f" />

<img width="504" height="174" alt="image" src="https://github.com/user-attachments/assets/05799c57-76ce-48b0-b31b-a5980ad9b032" />

#### 3. Follow the wizard to select the IMG file you need to flash

<img width="554" height="352" alt="image" src="https://github.com/user-attachments/assets/c95418a7-fc3f-40a4-844c-983650f24ad4" />

#### 4.Select your solid-state drive (SSD)

<img width="554" height="350" alt="image" src="https://github.com/user-attachments/assets/d2c1bd6a-eaa4-4ef1-a295-fa8585489d92" />

#### 5.Click Flash.

<img width="554" height="350" alt="image" src="https://github.com/user-attachments/assets/2cf36828-8744-4a16-b020-c1989ddb567c" />

<span style="color:red;">The above steps only flash the image file to your solid-state drive. Next, we need to modify the boot items, which requires the Ubuntu system. Please refer to the document [Method for Setting Up the Jetson Virtual Machine Environment in the materials and set up the Ubuntu environment](https://github.com/Elecrow-RD/AI-Starter-Kit-for-Jetson-Orin-Nano-with-Common-Board-design/blob/master/Solid-state%20programming/Method%20for%20Setting%20Up%20the%20Jetson%20Virtual%20Machine%20Environment.pdf) first.</span>

#### 6. Insert the solid-state drive (SSD) into the Ubuntu system

Enter the command lsblk to check the mounting status.


<img width="554" height="427" alt="image" src="https://github.com/user-attachments/assets/035ef0ee-14fd-4123-9092-fde5bb816ddf" />

As can be seen from the figure above, the SSD is mounted to the drive letter sdc.

Next,Enter the command sudo mount /dev/sdc1 /mnt to mount the first partition sdc1 of sdc to the /mnt directory of the Ubuntu system.

Use the ls command to check, and you can see that the root directory of JP has been mounted under this directory.

<img width="554" height="78" alt="image" src="https://github.com/user-attachments/assets/64a685ee-dc1e-4c47-8a21-3dbdf4c685dc" />

Enter the command: sudo blkid /dev/sdc1

query the PARTUUID.


<img width="554" height="78" alt="image" src="https://github.com/user-attachments/assets/0c131026-2e91-416f-a839-533c29add4ff" />

Finally: You need to modify the boot items.

Enter the following command sudo nano /mnt/boot/extlinux/extlinux.conf to open the boot configuration file.

<img width="554" height="430" alt="image" src="https://github.com/user-attachments/assets/251a2c73-1205-407a-8d74-411c04e44429" />

<img width="554" height="459" alt="image" src="https://github.com/user-attachments/assets/cec6a6b5-4333-4d63-90c5-b008e988bc9b" />

Make the following modifications:

<img width="554" height="461" alt="image" src="https://github.com/user-attachments/assets/8ea92ae9-4302-4aeb-a489-e6aa40ae1dfc" />

If the system image has been logged into before, you also need to modify the value of root below using the same method as above.



