# Fanuc Robot Unity

## Description
The latest Unity Project for the FANUC 2000iC robot has 16 Scripts inside the "For_Isabel" folder and 5 scripts inside the "HybridIK" folder
The Robot can be move through FK or IK directions but all the joints have a rotation limit.
The final joint of the Robot can grab and drop objects through a Configurable Joint

## Classes and Methods

*First Joint*
|__Variables__|__Type__|__Default Value__|__Description__|
|:---|---|---|---:|
|max|float|76| maximum rotation degree |
|min|float|-60| minimum rotation degree|
|current|float|0| current rotation degree|
|motion|float|0.1f| degree movement value |
|speed|float|1.0f | speed of rotation|

|__Class__|__Method__|__Description__|__Key__|
|:---|---|---|---:|
|FirstJoint|getEuler()|returns a Vector3 with the local rotation of the joint| NA |
|FirstJoint|RotatePositiveX_Joint1()|rotates first joint in positive x axis by adding a float number (motion * speed) to the current x position| x|
|FirstJoint|RotateNegativeX_Joint1()|rotates first joint in negative x axis by substracting a float number (motion * speed) to the current x position| x|
|FirstJoint|setSpeed(float)|sets the speed of the movement of the joint. It is controlled through the ScriptController| x|
|FirstJoint|getCurrentJoint1()|returns the local rotation of the Joint | NA |
|FirstJoint|setCurrent(float)|sets the current value for the joint rotation (it is useful to reset the value when changing from IK to FK)| NA |

*Second Joint*
|__Class__|__Method__|__Description__|__Key__|
|:---|---|---|---:|
|SecondJoint|getEuler()|returns a Vector3 with the local rotation of the joint| NA |
|SecondJoint|RotatePositiveX_Joint1()|rotates first joint in positive x axis by adding a float number (motion * speed) to the current x position| x|
|SecondJoint|RotateNegativeX_Joint1()|rotates first joint in negative x axis by substracting a float number (motion * speed) to the current x position| x|
|SecondJoint|setSpeed(float)|sets the speed of the movement of the joint. It is controlled through the ScriptController| x|
|SecondJoint|getCurrentJoint1()|returns the local rotation of the Joint | NA |
|SecondJoint|setCurrent(float)|sets the current value for the joint rotation (it is useful to reset the value when changing from IK to FK)| NA |

