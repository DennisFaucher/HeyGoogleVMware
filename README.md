# HeyGoogleVMware
Teaching Google Assistant to Control VMware
## Why
My electric company gave me a free Google Home for signing up and I needed to see what I could teach it to do. I have been blogging (blog.faucher.net) about interesting devlopments in VMware lately, so this seemed like a good idea.
## Requirements
* Google Home
* VMware installation. I used VMware Prallels, but vSphere could just as easily be used.
* IFTTT
* DropBox
* Keyboard Maestro for Mac (www.keyboardmaestro.com)
## How
### Connect IFTTT to Google Assistant and DropBox
Follow the instructions at these links: https://ifttt.com/google_assistant & https://ifttt.com/dropbox
### Create Google Assistant Skill in IFFTT
I created 4 Applets in IFTTT - Clone, Start, Stop, Enter. They are all pretty identical
Click Explore and the click + to create a new applet
You will see "If + This Then That"
Click on "+ This"
Search for "assistant" and then click Google Assitant
Click "Say a phrase with a text ingredient"
This is how I filled out my Google Assitant step for the Clone VM applet.
![Google Step](https://github.com/DennisFaucher/HeyGoogleVMware/blob/master/IFTTT%20Clone%20-%20Google.png)
Click "Create Trigger"
Now click on "+ That"
Search for "Dropbox" and then click Dropbox
Click "Create a text file"
This is how I filled out my Dropbox step for the Clone VM applet.
Click "Create Applet"

