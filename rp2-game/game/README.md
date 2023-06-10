
# Game Directory

The ___rp2-game___ directory contains game files and game executable as would be seen if you opened the CD in a file explorer. 

This game directory contains the modified cast files with English language translations. In other words, ___this is the translated game___. If you were looking to pack the game into a disc format (*.cue/bin, .img, etc*), burn to a disc, etc, you would pack ___game___, and nothing else.

# Running game from directory (NoCD)

___As of now, this has only been tested on a Windows XP Virtual Machine with Japanese Language Pack installed. There are no guarantees that this will work for any other system!___

*In the future, releases in disc image formats may be offered, which won't require a NoCD work around. At the moment, the purpose of NoCD for the convenience of modifying files without having to pack into a disc image format to test.*


## Steps to run game from game directory (Windows) (NoCD)

1. Create a virtual mapping of the game directory using the `subst` command. It is highly recommended to map to a drive letter starting from *G:* (*G:, H:, I:...*)


    Syntax:

    `subst <mapped drive letter> <path_to_game_directory>`


    Example:

    `susbt G: C:\Users\user\Desktop\rp2-fan-translation-eng\rp2-game\game`


2. We need to tell the game executable to run with certain parameters (*256 Colors, 640x480 resolution*). Since we cannot modify the executable directly since the machine thinks we are loading from a network drive, we will create a batch *(.bat)* file to run the game for us. We will pass in these parameters and load the game.


    .bat file syntax
    
    ```
        SET __COMPAT_LAYER= 256COLOR 640X480

        <path_to_RP2.EXE>
    ```

    .bat file example
    
    *rungame.bat*
    
    ```
        SET __COMPAT_LAYER= 256COLOR 640X480

        G:\WINSTART\RP2.EXE
    ```


3. Double click batch file and run game. If steps were completed successfully, you should be treated with a 640x480 screen and the game will begin running.
 ___Stability and compatibility may vary!___


## Tweaking settings

There is a file called *RP2.INI* in the *WINSTART* folder that contains settings for memory usage, graphics settings, and other odds and ends that can possibly be tweaked to improve performance. 
