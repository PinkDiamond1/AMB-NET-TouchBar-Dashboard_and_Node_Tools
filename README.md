# AMB-NET TouchBar Dashboard & Node Tools

![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/Node_Control_Touchbar_sm_.jpg)

### Hello fellow AMB-Net node operators. Welcome to this little repository.

!!! This Repo is no longer maintained as I'm no longer part of the Ambrosus community !!! Nodetools keep working but there is no guarantee for how long.

Here on the Repos main page I present a complete setup that may help you monitor and control your ATLAS or APOLLO node(s) through the MacBook TouchBar.

### Python Node Tools that make operating a node much easier.

In the Wiki section of this Repository you find other useful tools that run directly on your node(s) (_**and need no Mac**_), like a telegram notification tool, automatic payout tool for Atlas nodes with csv data collection and a tool to write Apollo rewards into a csv file automatically.<br>([Click here to go to the Wiki, as this main page is reserved for the TouchBar Dashboard guide](https://github.com/inlak16/AMB-NET-TouchBar-Dashboard/wiki))  

Please note that _this is NOT an official tool created by Ambrosus_, but a setup that I built to control my own node and found quite useful to share with the whole community. 
Although I don't expect any dangerous errors to occur, _I give no warranty that this is bug-free_, so please have a look at the code, before running it. I have been controlling my node with this for over a year without major issues now.<br>
_([Click here for an overview of Updates](https://github.com/inlak16/AMB-NET-TouchBar-Dashboard/blob/master/UPDATES))_

Also note that as soon as the AMB-Net API is altered in any way, the pulled node info might not work as expected anymore and changes to the code may be needed. Please get back to me on any edge cases you find. I'm posting all the code snippets seperately in here in the Code-Snippets subfolder so anybody can see what's going on.
_These code snippets can be encapsulated as executable apple scripts with Automator, too. So they may be useful even on a Mac without TouchBar._

![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/Node_Info_Touchbar_2.jpg)

### Installing BetterTouchTool

So let's get started. This setup only works with a tool called BetterTouchTool, which you can purchase for around 7 USD for a 2 year license or try for free for 45 days:

https://folivora.ai/buy

https://bettertouchtool.net/releases/BetterTouchTool.zip

For quite some time I have wondered if it was really worth it to get the more expensive MacBook with TouchBar. But now with this setup, it has gotten really useful. In the long run it is saving me alot of time that I would need for typing or searching and copying commands and the status overview is really useful.


### Overview of BetterTouchTool and Dashboard

After you have purchased your BetterTouchTool license and installed the software, 
just open it and import the _newest_ __AMB_Dashboard*.bbtpreset__ file (after unzipping), that I have put up here for download by using the preset function in the top right corner and click on import.

![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/01.png)


When the file has been loaded it should look like this (the new version has more layers than in this screenshot, but no worries, this is explained a little further down in the guide):

![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/02.png)



On the very left you have the programs that have TouchBar presets in them. Closer to the center is the area where so called triggers are layered. These are individual setups that contain code snippets and are fully customizable, in the end being the single building blocks of the dashboard. If you click on one of them, you see that the containing parameters are shown on the right hand side. One of the most important is the enabled/visible on TouchBar parameter to turn on and off single building blocks of the setup.



![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/03.png)



As you can see below, I tried to keep it as flexible as possible. From top to bottom there is a **login script** (opening terminal with ssh connection), **a group of several login scripts** (In case you plan to run several nodes now that the floodgates to onboarding are open :D ), **two price tickers** (the first in EUR or any desired currency (see instructions in the script), which runs through the free Coingecko API and the second in USD, running directly from AMB-Net API), **Apollo Online Status** (Online/Offline/Retired), **Apollo Main Stats** (Balance, Block, Stake), **Multiple Apollo Online Status 1-6** (little dots with a number indicating the nodes status in Green or Red), **Multiple Apollo Main Stats** (combined Balance and Stake of all nodes activated in script), **Atlas Online Status** (Onboarded/Offline), **Atlas Main Stats** (Balance,Sheltered Bundles, Stake), **Multiple Atlas Online Status 1-6** (little dots with a number indicating the nodes Status in Green or Red), **Multiple Atlas Main Stats** (combined Balance, Sheltered Bundles and Stake of all nodes activated in script),**two reward estimators** (the first in EUR or any desired currency, running with the free Coingecko API and the second in USD, running directly from AMB-Net API.) and **AMB-Net Stats** (Daily Bundles, AMB per Bundle).


<img width="600" alt="portfolio_view" src="https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/06b.png">

To give a better overview, here are 4 setups with different triggers activated and its resulting Dashboard that is activated by holding **Shift Command** on the keyboard.

**AMB USD - Atlas Online Status - Atlas Main Stats - Rewards USD - AMB-Net Stats**:
![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/08.png)

**AMB USD - Multiple Atlas Online Status (1-6,No5 offl) - Multiple Atlas Main Stats - Rewards USD - AMB-Net Stats**:
![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/08b.png)

**AMB USD - Apollo Online Status - Apollo Main Stats - Rewards USD - AMB-Net Stats**:
![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/09.png)

**AMB USD - Multiple Apollo Online Status (1-3) - Multiple Apollo Main Stats - Rewards USD - AMB-Net Stats**:
![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/09b.png)

### Setting up your node in the Dashboard

The addresses set for demonstration purposes are just the longest running nodes I could find and are likely run by Ambrosus.
Now lets add your node in there.
Set visibility of layers according to your nodetype ATLAS or/and APOLLO (each single or multiple) and click on it's according online status layer. For multiple repeat this step for each node you want to monitor. 
If you run both Atlas and Apollo nodes, I suggest you activate the needed layers and change the keyboard shortcut for all building blocks of either Atlas or Apollo to something else than the standard setting of Shift Command in the Common Settings of the layers.
This gives you two quickly readable dashboards of both your Atlas and Apollo nodes.

On the right side there is the option to switch between common, which is mainly UI settings and widget-specific, which contains the whole Applescript to pull a nodes online status into the dashboard.
Just enter your nodes public address into the script und click save at the top when the option comes up.



![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/04.png)



After doing the same with the according Main Stats Layer, the **Shift Command** Dashboard already works.

A **Multiple Main stats** Layer needs you to set the **nodeactive** _variables in the script below the nodeaddresses_ to define which node slots of the 6 given to pull data from. Set either 1 to activate or 0 to deactivate.

Activating the Online-Status-Layer again, now click on the "run apple script" at the top center.
This triggers commands when pushing the area of the TouchBar where the building block/layer is appearing.



![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/07.png)



If you add your nodes public address in here, holding **Shift Command** and pushing on the Online Status of your node on the TouchBar opens the Ambrosus Explorer with your nodes page in Brave. If you dont have the Brave browser installed, you can change the script to any other browser.
For a setup with multiple nodes you need to repeat this for every visible Online-status-Layer and its corresponding nodeaddress to be able to access all your nodes explorer pages by tapping the status dots on the TouchBar. 

Pushing the price ticker on the TouchBar opens Ambrosus Reddit, Ambrosus Twitter, Coinmarketcap and Romans great reward-calculator amb.money.

Tapping the grey AMB-net Info part of the Dashboard on the TouchBar opens the main page of the Ambrosus-Explorer.

For an accurate estimate of rewards to be calculated, be sure to set the first lines in the **NODE REWARDS ESTIMATE USD/EUR** script according to the nodes/stakes you are running. You have the option to deduct taxes from the results and show Bundle- and Blockrewards seperately for Apollo. Tapping on this reward section on the TouchBar opens Amb.money.

![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/reward.png)

Note that Atlas Node Rewards are distributed over the timeframe of 1 year to incentivise keeping bundles available for the network. Similarly Apollo Bundle Rewards are not equally distributed every day, but average out over a longer time period. See Payout-Scheme made by community member CaptainCrypto for Atlas Nodes below:

![alt text](https://camo.githubusercontent.com/4ca5cef1b8d18e56e8dc33ccb209dd0c7874609bec87f61918580586874c6334/68747470733a2f2f696d672e696d61676575706c6f61642e6e65742f323032302f31302f32302f41746c61732d2d2d7265776172642d73797374656d2e706e67)

### Logging into your node and setup of the Terminal Background for aesthetics and orientation

Now that we have the visuals going, lets get to the control Dashboard.
As mentioned in the beginning, the top layers in BetterTouchTool are for logging into one or multiple nodes. You gain access to the scripts again with the run apple script button. Just input your user@ip and save. If you use several ssh keys, use the **-i flag** to define the key you want to use. 

![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/10.png)

You can create a preset in terminal with a background image for your node. And if you run more than one node, the apple script would switch the background according to the node to give a better visual overview of where you are logged in. If you use the Exit scripts that are on every level of the control Dashboard, the Terminal preset is automatically reset to Basic. If you are not using this, you may have to create a preset in Terminal called Basic or alter the exit scripts. 

I've uploaded a PSD Photoshop file and created some network graphics variations, so you can fully customize your node backdrop image with your Server location and public address in Photoshop or Gimp (which you can download for free here: https://www.gimp.org/downloads/ ). For those of you that don’t want to fiddle around with graphics software, 
I have generated some variations of the Backdrop and uploaded them here as png images and bundled as zip file for easy download aswell. All of these can be found in the Node-Backdrop folder. Feel free to use them as you like.


Layer overview of the Photoshop file:
![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/15.png)


Terminal Profile Settings with preset "Amb1" having loaded a Backdrop image called "Amb_node_1.png"              
(I found terminal window size 150x50 to be a good preset):
![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/11.png)


When you are logged in through the >_ button on the touchbar, BetterTouchTool automatically switches to the Triggers for the Terminal application on your TouchBar. There are two options on the top level. Analysis and Node Control.
![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/14.png)

### Analysis functions on the control Dashboard

Tapping on Analysis on the TouchBar gives all kind of options. 

From left to right here are the scripts in the Analysis Group that you can scroll through on your TouchBar:
**Atlas Logs 1h - Parity Logs 1h - Sheltered Bundles - TimeServer - TempBannedIP - BruteForce Protection - Granted Logins - Failed Logins - SSH Connections - Parity Version**
![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/13.png)

Just disable unneeded functions by turning off their Triggers visibility in BetterTouchTool.

![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/Analysis_Touchbar_sm.jpg)

**The Atlas Logs 1h** shows challenges for Atlas nodes and **Parity Logs 1h** shows the Blockchain connection through its Peercount (should be higher than 15 in my experience) and Blockheight (if node is showing offline, compare the Blockheight with the Ambrosus Explorer and see if the node is still syncing).

The **Sheltered Bundles** function gives ATLAS node operators certainty of the Bundles held on their nodes harddrive.
If you tap this on the TouchBar, it outputs a text in Terminal with the number of sheltered Bundles in the very last line.

**TimeServer** returns the connection to different ntp timeservers and its delay. I have this installed to be sure that my node has the correct time. You can install ntp simply by running the following. The last line is the same as in this function to query connection to timeservers:

```
sudo timedatectl set-ntp off
timedatectl status
sudo apt install ntp
ntpq -p
```

**TempBannedIP** is a function that calls a list of ips that have been banned through the BruteForce Protection.
I'm using fail2ban to permit bots and hackers from bruteforcing into my node. You can install the software by following these steps:

```
sudo apt-get install -y fail2ban
sudo systemctl start fail2ban
sudo systemctl enable fail2ban
awk '{ printf "# "; print; }' /etc/fail2ban/jail.conf | sudo tee /etc/fail2ban/jail.local
sudo nano /etc/fail2ban/jail.local
```

This installs fail2ban and copies the configuration file so that you can easily modify the settings to your needs.
After running the last line the nano texteditor should be opened with the configuration file jail.local.
Here you go down in the text, until you find the following 3 parameters: Max retry, Findtime, Bantime.
Erase the # in front of every one of those parameters + in front of the previous DEFAULT several lines above to activate this whole settings block. Then enter maximum login attempts as max retry, the time a user has to try these number of login attempts  (Findtime) and the time an ip is banned for (Bantime), if these tresholds are crossed. Note that this rule applies to your login device aswell.
So if you set 5 retries and 5000m bantime and type your ssh password wrong 5 times, your computers ip is banned for over 83 hours. After setting these variables as you like, quit nano with **Control X** and save the file. Now restart fail2ban:

```
sudo systemctl restart fail2ban
```
Now use the function **BruteForce Protection** on the TouchBar in the Analysis Group. The status should be returned with a green text showing that the protection is _active_. If it doesn't, check if you erased the # in front of the DEFAULT above the changed parameters in the jail.local text file. After you have it showing _active_, the **TempBannedIP** function returns the content of the ban list that is generated by malicious login attempts. After a few days you should see some ips there already. Every now and then the ban list is reset, so don't worry, if the ban amounts get smaller at some time. 


With the **Granted Logins** function you can check, who logged into your vps successfully. Quit with **Q** .

**Failed Logins** of course returns the opposite. And it's quite astonishing how many bots must be out there to try on all kind of ips all day.

The function **SSH Connections** returns just the attemps that have been made with ssh connection.

With **Parity Version** you can simply check which version of parity your node is running to know if an update is needed.

And that's it for the Analysis part.

### Controlling your node on the Dashboard

The Node control part of the Terminal controls of the Dashboard is pretty self explanatory.
From left to right you can run the Atlas Payout command in yarn, stop the node, update the node and/or the system, start the node again, resync the chain (using a blockchain image file to speed up the process) and run diagnostics (only works, if you run your node from root).

![alt text](https://github.com/inlak16/AMB-NET-Touchbar-Dashboard/blob/master/tutorial-images/16.png)

### Automatically tracking Noderewards to a CSV-File through python on the node

Here is a solution and guide to track daily apollo noderewards automatically into a csv file directly on the node through python for up to 6 nodes.

[Track daily Apollo rewards through Python](https://github.com/inlak16/AMB-NET-TouchBar-Dashboard/wiki/Track-daily-Apollo-rewards)

For Atlas nodes there is a solution aswell that automates payout, tracks rewards in a csv-file and optionally sends out payout funds to another account.

[Automate Atlas payout, track rewards and optionally send out funds through Python](https://github.com/inlak16/AMB-NET-TouchBar-Dashboard/wiki/Automate-Atlas-Payout,-track-rewards-and-optionally-send-to-another-account)


[Here is a link to the Updates that have been done so far](https://github.com/inlak16/AMB-NET-TouchBar-Dashboard/blob/master/UPDATES)






