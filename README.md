# How to move your iRacing data files out of your Documents folder
A guide for using symlinks to move your iracing data off your operating system drive


This will allow you to have your iracing data (for me setups and replays most importantly) in a seperate location or drive from your main OS drive (usually C)

iRacing by default doesn't let you change where this is saved but using symlinks we can trick it into thinking its there but actually put it somewhere else!

## Move the folders out of the iRacing Documents folder

First off, cut and paste your replay directory into the place you want them to live, in my example I used `D:\iRacing\replay` to sort of match the default. My D Drive is a seperate hard drive with much more space than my C drive SSD.

Then we're gonna run a command that will create a symlink or junction that will make essentially a shortcut that iRacing can use to access these files in the new location as if they were in the correct place.

## Open the Command Prompt as Administrator

Open up a command prompt as an administrator by finding it in your start menu (usually by typing command prompt), right clicking it and selecting Run as Administrator.

![image](https://user-images.githubusercontent.com/33838911/167403610-63e5f2f5-6d44-47e0-97bd-a5cf4911e0ce.png)

We will use the mklink command to create our new special folder in the iRacing directory. Make sure the original folders are moved to their new home and don't exist in the iRacing directory before proceeding.

You will need to find what your iRacing data directory is inside your Documents folder. This should be `C:\Users\*YOUR_USERNAME_HERE*\Documents\iRacing` but you can check by clicking here in the folder.

![image](https://user-images.githubusercontent.com/33838911/167404349-f4566c25-cd8f-4c8f-813b-5513608fc94c.png)

You also need to know the directory of where your files are now living, you made this earlier to contain them when you moved them. Mine is `D:\iracing`

## Make the link

Now we're gonna make our link.

In the command prompt we opened earlier, enter this command. Make sure you actually edit it before entering it because the specific locations are going to be different for your computer!!

`mklink /J "C:\Users\*YOUR_USERNAME_HERE*\Documents\iRacing\replay" "directory of where your files are living now"`

replace your username and the 2nd directory with wherever your files are now living!!

So mine for example was 

`mklink /J "C:\Users\Leah\Documents\iRacing\replay" "D:\iracing\replay"`

![image](https://user-images.githubusercontent.com/33838911/167405253-836f57ae-7c28-41d8-8ba1-bdef0b355b25.png)

You'll see a similar message in your command prompt if you've done it right. Make sure to double check everything is matching!! Any wrong characters will mess it up.

The basic syntax is `mklink /J "the location you want to create the fake folder at" "the place where the files actually live"` if you want to use this elsewhere.

If you check your iRacing Documents folder, there should be a folder there now with a little icon and double clicking it should take you directly to your new folder where your files are living. iRacing will essentially do the same thing when it's accessing your files and will be none the wiser that they're actually vibing elsewhere.

![image](https://user-images.githubusercontent.com/33838911/167405513-9a0b45a6-8c34-4d85-b0d6-7b96e3e79234.png)

You can repeat this for other folders, for example setups and paints.

This should hopefully free up some space on your C drive. It should be illegal to automatically save stuff to Documents or appdata i s2g please help
