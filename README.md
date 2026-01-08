# The advance media playback stack ultimate to watch video on your PC


In this build I'm trying to avoid all unnecessary data processing hops to increase processing speed and reduce letencies and it will help to bring media content on your screen as closer to the original as it's possible with less compressings, transformations, corrections... etc. Basic idea here if you do not know for what it is better turn it off. Also this guide will help you to dive into ocean of high quality video playback with all this acronyms and preferences which we are usually prefer to do not touch and to use VLC Player instead... lol.
This is just one of the examples and it doesn't claim to be perfect or only one right. This is just a base for you. Most of this options are very subjective because everybody have their personal preferences, but anyway some point's are very preferable to be turned on or turned off, so let's go through my setup and I will try to explain as much as I can and as much as I know by myself. But I need to warn you that like for most such setups something can go wrong on different OS or hardware so you and only you responsible for your actions.
So let's start!

# PREPARATION
Typical media stack can be divided into these steps: Player > Splitter > Filter > Renderer.

So let's decide and download all this ingredients for media stack.

[DAUM PotPlayer](https://potplayer.daum.net/) - one of the coolest players on the market made by Korean studio "Kakao". It's convenient to use and flexible to modificate. Also it's completely free.

[LAV Filters](https://github.com/Nevcairiel/LAVFilters/releases) -  - most complete and up to date open-source pack for splitting and decoding audio and video streams. Guy with nickname "Nevcairiel" and community doing really great job.

[madVR](https://www.videohelp.com/software/madVR) - complete solution that includes best algorithms to increase quality of video stream. It's done buy guy with nickname "Madshi" and highly supporting with community. It's a heavy but precious gem.

[XySubFilter](https://github.com/Cyberbeing/xy-VSFilter/releases) - advanced filter for subtitle processing that supported by user with name "Cyberbeing" in collaboration with "Madshi".

For ASIO I created separate chapter in this guide because it's very optional and specific.

# INSTALLATION
Please pay attention that I'm performing all installations and launches under administrator rights: Right click on the file you want to launch > Run as administrator.

Installation of DAUM PotPlayer is pretty simple. After installation it will ask you for additional downloads of OpenCodec pack. Originally it was integrated in PotPlayer directly but after time it was separated due to some license problems. We are going to use LAV Filters, so not need in OpenCodec here.

Same story with LAV Filters installation - it's pretty simple to do. Installing only x64 versions. Also do not forget to set check-boxes near all possible formats to support.

For madVR this process is a little bit different. We have archive that firstly need to be unpacked and copied in your "Program Files" folder. After this you can execute "install.bat" file inside this folder. If in the end you see cmd window with "Installation succeeded." you can be sure that installation passed without problems.

XySubFilter installation process is the same to madVR - we need to unpack archive and copy in your "Program Files" folder. After this you can execute "Install_XySubFilter.bat" file inside this folder. If in the end you see cmd window with "Installation succeeded." you can be sure that installation passed without problems.

Here it is! We've installed everything we need.

# SETUP
### 1. Disabling default player transformation and splitting

To avoid any unnecessary hops and data transformation first at all let's disable default built-in transform filters in player.

PotPlayer > [RMC] > Preferences > Filter Control

In "Video Transform Filter Usage" dropdown select "Disable" option.

Uncheck "Use Built-in Audio transform Filter" check-box.

Uncheck "Use Built-in Audio Stream Switcher" check-box.

Uncheck "Use Built-in Audio Stream Switcher (Alternative)" check-box.

<img width="751" height="564" alt="002" src="https://github.com/user-attachments/assets/45e5f139-6534-4cfb-b402-17d3cf305655" />

Apply > OK

### 2. Passing transformation and splitting to LAV Filters

Let's add LAV Filters in the filter list one by one.

PotPlayer > [RMC] > Preferences > Filter Control > Source/Splitter > Filter Management

Press on "Add registered filter..." then select "LAV Splitter" and hit "OK".

Press on "Add registered filter..." then select "LAV Splitter Source" and hit "OK".

Press on "Add registered filter..." then select "LAV Audio Decoder" and hit "OK".

Press on "Add registered filter..." then select "LAV Video Decoder" and hit "OK".

Make sure all 4 filters now in "DirectShow Filter List" and only them. Also make sure check-boxes near them are chacked.

<img width="758" height="551" alt="003" src="https://github.com/user-attachments/assets/250a1a6c-a290-4f53-a416-a0569bec623d" />

Now we need to associate every of them with proper source types.

Select "LAV Splitter" in "DirectShow Filter List" by pressing on it and check every check-box in "Source/Splitter" list.

<img width="758" height="551" alt="004" src="https://github.com/user-attachments/assets/721e4908-09cc-48cf-89e4-ee75040ce183" />

