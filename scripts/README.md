# Cast name and dimension editor script

This script is a lingo script intended for use with Director 5. It serves multiple purposes.

- Rename cast member after replacement

  When we are working inside of a cast in Director, we delete the original cast member (image) and replace it with our own image, which creates a new cast member. Since in-game scripts and logic relies on cast member names, we set the new cast member's name to the original cast member's name.

- Set regPoint of new cast member to regPoint (registration point) of old cast member.

  This is similar to the other bullet point. When we bring in our new cast member, the regPoint is set to (0,0). We set the regPoint back to the original member's regPoint. The regPoint property of a cast member is the point coordinates of a member in point form [as defined here](https://help.adobe.com/archive/en_US/director/UsingScripting/director_reference.pdf).

- Determine and set new regPoint if the new cast member's photo's dimensions do not match the old cast member's photo's dimensions

  When we have resized a translated image (to allow for more space for text, etc.), we need to figure out the new regPoint for the cast member so that the asset is positioned correctly in the scene. The formula for finding the new regPoint is:
    ```
        point(new_width/2, original_y + (new_height - original_height)/2
    ```
To use this script, we currently import the original cast (```source_*``` in the script.. the original game file) and the cast we are modifying. We open the script window, and make sure that the cast member that we are adding this script to is a movie script (i.e. it is not in any of the casts we are modifying or reading from). We set the values of ```source_cast_name``` and ```target_cast_name``` to their respective file names (it is recommended to rename the source_cast_name, so you can differentiate between the two in Director). Logging statements can be viewed in the 'Message' window in Director. The script will loop over each cast member and do the actions mentioned above.

Note: **Use copies of the source and target cast!! Don't modify the source cast!!**
  
