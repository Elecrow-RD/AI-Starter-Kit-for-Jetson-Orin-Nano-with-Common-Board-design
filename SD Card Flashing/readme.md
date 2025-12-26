### Method for Jetson SD Card Image Flashing

1. Prepare an empty 128GB SD card (if it is not formatted, you can use the **SDFormatter.exe** software for formatting).

2. Download the image file to the local device, e.g., download the file **jetson20251216.img** to your local storage.

3. Launch the software **Win32DiskImager.exe** in the folder **ImagerWrite**.

4. Select the image file that has just been downloaded to the local device, such as the file **jetson20251216.img**. The device will automatically select your SD card; if not, select it manually.

5. Check the option **Read Only Allocated Partitions**, then click **Write**

<span style="color:red;">Note: Here, **Write** means to write the data of the img image file to the SD card, while Read means to read the data from the SD card into the **img** image file. Be sure not to mix up these two operations.</span>

<img width="497" height="348" alt="image" src="https://github.com/user-attachments/assets/2ea49691-bcdd-4ded-982c-66a4b939f23f" />

6. After the image writing is successfully completed, eject the SD card, insert it into the Jetson device and power it on. The boot password is **elecrow**.
