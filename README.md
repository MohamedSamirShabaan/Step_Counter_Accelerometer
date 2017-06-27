# Step_Counter_Accelerometer
Android App calculate number of steps by the Accelerometer sensor using some statistics methods. 


# Description :
this app run in all Android API becasue this app doesn't use STEP_COUNTER or STEP_DETECTOR sensors

this app use the Accelerometer sensor only in addition to some simple statistics methods.

# Idea:

every one second the sensor read 5 values for acceleration in directions x, y and z.

	(5 reads per second due to we use SENSOR_DELAY_NORMAL uo can use another like SENSOR_DELAY_UI)
	
	calculate the magnitude (mag)^2 = x^2 + y^2 + z^2 and save mag in list NOTE: mags is the samples
	
	(why we use the magnitude? as magnitude remove the direction, this manage us to count steps in all directions)
	
 
once you click on COUNT statistics roll will come

	calculate the mean (avarage of mag in list)
	
	then calculate the standard deviation (std) which refer to the sum of all differences between all mags in list and the mean divided by the number of mags (samples)
	
	begain to count the peaks which have mag greater than std and this is the number of steps
