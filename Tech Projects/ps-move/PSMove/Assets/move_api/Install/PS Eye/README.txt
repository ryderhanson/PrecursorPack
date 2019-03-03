Installing PS Eye
-----------------
Adapted from https://github.com/cboulay/psmove-ue4/wiki/Windows-PSEye-Setup
-----------------

1. Insert PS Eye into USB 2.0 port or above. Should appear as 'USB Camera-B4.09.24.1' or something similar
   in device manager.

2. Run Zadig and install libusb-win32 onto 'USB Camera-B4.09.24.1' (Interface 0 on my machine)
	Notes: - Don't install onto 'Interface 1', this will already have usbaudio installed.
	       - If no devices appear for installation tick "Options->'List All Devices'"

3. Test the performance of the camera with 'test_camera.exe'.
	If there is visible tearing/laggy footage:
	       - Try installing the WinUSB driver with Zadig instead.
	       - Make sure the Eye is the only usb device connected to the usb hub.