Using the Move UDP Server
-------------------------

Set Up / Testing
----------------

1. First of all, go to 'install/PS Eye' and 'install/PS Move' and get the hardware set up.

2. Try a few of the test applications. The Processing example requires 'move_udp_server.exe' to be running.

Move UDP Server
---------------
Bind to IP: '127.0.0.1'
	Port: 23459

The server sends 2 different messages.
	- Type 'a': Move Physical Data (High frequency, around 100hz)
	- Type 'b': Move Positional Data (Slower, depends on machine)

--------------
Type A
--------------
Sent in format: msgType, msgNo, controller, currButtons, triggerVal, ax,   ay,    az,   gx,   gy,   gz,    mx,    my,   mz
Eg:		a        1022   0           128          54          1.000 -0.456 0.234 0.123 0.123 -0.435 -0.363 0.234 0.635

msgType:     char - 'a'
msgNo:       int - Begins at 0 and increments each 'a' type message
controller:  int - Controller number (starts at 0)
currButtons: int - Between 0-255. Stores button presses bitwise.
		   CROSS,SQUARE,TRIANGLE,CIRCLE,MOVE,START,SELECT,PS
	     eg  - 01001000 Means SQUARE and MOVE are pressed.
triggerVal:  int - Between 0-255, 0 means trigger is unpressed, 255 means fully pressed.
ax,ay,az:    float - Accelerometer values. Measured in 'g'. Standing the move on its end approx az = -1.
gx,gy,gz:    float - Gyroscope values. Measured in rad/sec. x-axis pitch, y-axis yaw, z-axis roll.
mx,my,mz:    float - Magnetometer values. Between -1 and 1. 

--------------
Type B
--------------
Sent in format: msgType, msgNo, c, tx,   ty,   tz,  ux,    uy,   trackingMove
		b        52313  0  10.24 20.53 10.3 0.0353 0.623 1
msgType:     char - 'b'
msgNo:       int - Begins at 0 and increments each 'b' type message
controller:  int - Controller number (starts at 0)
tx,ty:       float - x and y position of the ps move blob measured in cm from the center of the camera.
	     Note that as you move further from the camera you can get further horizontally/vertically
tz:	     float - z position of the ps move blob measured in cm.
ux,uy:       float - normalised x and y positions. (between 0 and 1, although the tracker fails around 0.05 and 0.95)