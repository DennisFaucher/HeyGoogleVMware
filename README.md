# HeyGoogleVMware
Teaching Google Assistant to Control VMware
## Why
My electric company gave me a free Google Home for signing up and I needed to see what I could teach it to do. I have been blogging (blog.faucher.net) about interesting devlopments in VMware lately, so this seemed like a good idea.
## Quick Demo Video
Demo Video: https://youtu.be/enyho_JCdhg

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

![Dropbox Step](https://github.com/DennisFaucher/HeyGoogleVMware/blob/master/IFTTT%20Clone%20-%20Dropbox.png)

Click "Create Applet"

### Create the folder in DropBox
(It is assumed that Dropbox is installed on your Mac)

Create the folder(s) in Dropbox that you referenced in your IFTTT applet(s)

From the example above, the folder /Users/[username]/Dropbox/Clone

### Create the action in Keyboard Maestro
(It is assumed that Keyboard Maestro is installed on your Mac)

Create a new global macro named "Clone VM" You can import the actual macro from this GitHub repository. I am brand new to Keyboard Maestro, so there might be more elegant wys to get this done. This works though :)  

Here are a few screen shots:

![Macro - Top](https://github.com/DennisFaucher/HeyGoogleVMware/blob/master/KM%20-%20Clone%20Top.png)

![Macro - Bottom](https://github.com/DennisFaucher/HeyGoogleVMware/blob/master/KM%20-%20Clone%20Bottom.png)

The star of all these VMware macros is the /usr/local/bin/prlctl command which is the CLI to VMware Parallels. 

### Create a Parallels Template
Choose one of your VMs, choose Clone to template from the File menu. To help Google assitant, name this template one word, all lowercase. 

## Test
For debugging purposes, I suggest having your VMware Parallels window, and your Dropbox/Clone Finder window visible. Any success/failure messages from Keyboard Maestro will be placed in your Mac Notifications sidebar. I also logged results in a Results.txt file in Dropbox.

Say "Hey Google, Ask VMware to clone [templatename]"

You should see the file VM_Clone.txt show up in Dropbox, the template get cloned to a new VM named [templatename]timestamp, and then VM_Clone.txt get deleted.

Congratulations!
