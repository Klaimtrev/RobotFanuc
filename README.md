# Fanuc Robot Unity

## Description
The latest Unity Project for the FANUC 2000iC robot has 16 Scripts inside the "For_Isabel" folder and 5 scripts inside the "HybridIK" folder
The Robot can be move through FK or IK directions but all the joints have a rotation limit.
The final joint of the Robot can grab and drop objects through a Configurable Joint

## Sections
  [First Joint](#first-joint)
  [Second Joint](#second-joint)
  [Third Joint](#scripts-controller)

## Classes and Methods

### First Joint

|__Variables__|__Type__|__Default Value__|__Description__|
|:---|---|---|---:|
|max|float|185| maximum rotation degree |
|min|float|-185| minimum rotation degree|
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

### Second Joint
|__Variables__|__Type__|__Default Value__|__Description__|
|:---|---|---|---:|
|max|float|76| maximum rotation degree |
|min|float|-60| minimum rotation degree|
|current|float|0| current rotation degree|
|motion|float|0.1f| degree movement value |
|speed|float|1.0f | speed of rotation|

|__Class__|__Method__|__Description__|__Key__|
|:---|---|---|---:|
|SecondJoint|getEuler()|returns a Vector3 with the local rotation of the joint| NA |
|SecondJoint|RotatePositiveY_Joint2()|rotates first joint in positive Y axis by adding a float number (motion * speed) to the current x position| x|
|SecondJoint|RotateNegativeY_Joint2()|rotates first joint in negative Y axis by substracting a float number (motion * speed) to the current x position| x|
|SecondJoint|setSpeed(float)|sets the speed of the movement of the joint. It is controlled through the ScriptController| x|
|SecondJoint|getCurrentJoint2()|returns the local rotation of the Joint | NA |
|SecondJoint|setCurrent(float)|sets the current value for the joint rotation (it is useful to reset the value when changing from IK to FK)| NA |


### Scripts Controller
|__Variables__|__Type__|__Default Value__|__Description__|
|:---|---|---|---:|
|RecordNumber|int|0| Number of the first line where the reader will get the coordinates from|
|joint1R|float| NA | float value where the rotation of the joint will be stored|
|joint2R|float| NA | float value where the rotation of the joint will be stored|
|joint3R|float| NA | float value where the rotation of the joint will be stored|
|joint4R|float| NA | float value where the rotation of the joint will be stored|
|joint5R|float| NA | float value where the rotation of the joint will be stored|
|joint6R|float| NA | float value where the rotation of the joint will be stored|
|pickUpObj|bool| NA | boolean that indicates wether an object was picked up or not|
|StringLength|int| NA | length of the coordinates |
|speed|float|1.0f | speed of rotation|
|lastStep|float| NA | stores the time between lastStep (used for shift key)|
|timeBetweenSteps|float| 0.1f| indicates the time to count before it accepts the same input again (used for shift key)|
|list1|List<string>| NA| List to store all the coordinates extracted from log.txt|
|firstJoint|FirstJoint| NA| Gets a reference to the First Joint Script|
|secondJoint|SecondJoint| NA| Gets a reference to the Second Joint Script|
|thirdJoint|ThirdJoint| NA| Gets a reference to the Third Joint Script|
|fourthJoint|FourthJoint| NA| Gets a reference to the Fourth Joint Script|
|fifthJoint|FifthJoint| NA| Gets a reference to the Fifth Joint Script|
|sixthJoint|SixthJoint| NA| Gets a reference to the Sixth Joint Script|
|Joint1Object|GameObject| NA| Gets a reference to the first Joint|
|Box|GameObject| NA| Gets a reference to the object|
|Target|GameObject| NA| Gets a reference to the Target for the IK|
|IKtoggle|bool| true| A boolean used to check and turn off/on IK|

|__Class__|__Method__|__Description__|__Key__|
|:---|---|---|---:|
|ScriptsController|createPositionRecord()|records the local rotation of all the joints| NA |
|ScriptsController|CreateText()|creates the log.txt file if it does not exists| u |
|ScriptsController|ReadString()|reads log.txt and adds every line to the list1| x|
|ScriptsController|IncreaseSpeed()|increases the speed of all joints of the robot| shift|
|ScriptsController|DecreseSpeed()|decreases the speed of all joints of the robot| ctrl|
|ScriptsController|findIndex(char, string)|finds the index of # from list1 and returns an int[] with the locations of all of them | NA |
|ScriptsController|loadMovementRecord(int)|loads the coordinates for each joint based on list1 and findIndex| l |
  
# List of errors (x means solved)
- [x] Picking multiple objects
- [ ] Store picking up method inside log.txt
- [ ] Picked object does not follow robot's movement
