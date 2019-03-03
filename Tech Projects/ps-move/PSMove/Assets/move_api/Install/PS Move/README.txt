Installing PS Move
------------------
Adapted from: https://github.com/cboulay/psmove-ue4/wiki/Windows-Controller-Setup
------------------

1. Make sure the controller has charge before beginning or you won't be able to pair via bluetooth.
   I had trouble getting the controller to charge on Windows 10 :(
   To my knowledge it charges on Windows 7 and Mac well.
   When the controller is charged pressing the 'PS' button will cause the LED on the controller to flash.

2. Use the 'psmovepair.exe' utility to save the Bluetooth address to the controller. The util will fail past this point though.

-------
Warning: This step is easily the most frustrating. The controller seems to pair fairly randomly, once it does pair it works well.
-------
3. Run 'psmove-pair-win.exe' (from https://github.com/nitsch/psmove-pair-win) 
   Press the 'PS' button and allow the utility to run. If the LED stops flashing press the 'PS' button again.
   Basically continue this process until you get a successful connection, there doesn't seem to be a trick to it unfortunately.
   Note: If the controller is low on battery a successful connection can look like its still pairing (flashing LED)

4. Once the controller has paired run the 'magnetometer_calibration.exe' utility. 
	- Rotate the controller until you get a value 250+
	- Stand the controller on its end on a flat surface with the 'PS' button facing you.