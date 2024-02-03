+++
title = "How to Download Everything On The Internet"
date = 2024-01-30T11:23:30-07:00
+++

### *Secretly an intro into working with command-line*

<br>

##### *Not as scary as it sounds, I promise!*

<br>

No more going to sketchy websites for downloading YouTube videos, Twitter videos, songs off Soundcloud, songs off Bandcamp, etc. There is a way to download content from these sites directly and easily with no sketchy website, all from an application on your computer. You can set this up on any OS, but I'm specifically going to show you how to set it up on a Windows 10 PC, because that's what I have, and stats show that's probably what you have too.

<br>

The application is called [yt-dlp](https://github.com/yt-dlp/yt-dlp)! I'm making this tutorial because I genuinely think everyone should know how to use yt-dlp, and because installing yt-dlp, for the average person, is actually kind of complicated. I also somehow cannot find any really comprehensive guides that start from the absolute beginning for people with Windows PCs.

<br>

## Step one! Kind of...

<br>

Download yt-dlp! Usually, with normal programs, you'd just go to it's website and click the big "DOWNLOAD" button, and there you have it. Not with yt-dlp. yt-dlp is a command-line program (which if you don't use command-line programs, that may sound scary, but I promise it isn't, and learning how to download and use command-line programs can be very useful.). These are the steps to download yt-dlp:

<br>

`1.` Install python through it's website.
<br>
`2.` Install pip using python through command-line.
<br>
`3.` Install yt-dlp using pip.

<br>

## Step one, actually!

<br>

So the **actual** step one to downloading yt-dlp is to download python. You can do that at the [python.org downloads page](https://www.python.org/downloads/windows/). Click whatever the top link in the "Stable Releases" column is, scroll down on that page to the "Files" section and click the "Windows installer (64-bit)". It'll probably be somewhere at the bottom of that list. Once you click that, It should install, and you can run that application and setup python!

<br>

## Step two, pip:

<br>

After python is installed, we can to do step 2: install pip, which allows us to install yt-dlp. To install pip we use Python in the command line. To open the command line on Windows 10, I press Win-X, this opens a menu with a bunch of different pre-installed Windows apps, then you can just click "Command Prompt" (or you can just press A with that list open, which is what I do) and it'll open the command line. You're going to need the command-line for the rest of this tutorial. To test if you installed Python correctly, type this into command prompt:

<br>

`python --version`

<br>

It should say "Python 3.10.4" or something like that, the verison number might be slightly different for you. If it doesn't say that and gives you an error saying something like "'python' is not recognized as an internal or external command", then you installed Python incorrectly. Once you install it correctly, pip might of been installed automatically when you installed Python. To check that, type this in the command line:

<br>

`pip --version`

<br>

If it gives you a version number, great! Go to step three. If it doesn't, type:

<br>

`python get-pip.py`

<br>

And that should install it. Test again using "pip --verision" and it should give you the version number, then you can go to the next step.

<br>

## Step three, yt-dlp:
### *Finally!*

<br>

After pip is installed, we can finally install yt-dlp! Just type:

<br>

`pip install yt-dlp`

<br>

And it should start installing. Once it's done, test it by typing:

<br>

`yt-dlp --version`

<br>

And, if you get no errors, you're good to start using yt-dlp! But before I show you how to download anything, let me explain a little about what you've been looking at in your command prompt. That text before where you type is telling you where your working directory is (it probably says something like "C:\WINDOWS\system32"). Anything you download with yt-dlp will download in whatever your current working directoy is, *which is annoying!* But we luckily can change the default download directory, so it ignores whatever your command line working directory is, and downloads to the same folder every single time. Before we do that though, lets download something, just to check that everything is working.

<br>

## Brief summary on downloading:
### *Mostly a summary on changing directory.*

<br>

First let's change our directory so aren't downloading a video into our system32 folder. To do that we just type "cd" followed by whatever directory we want to download to (cd standing for "change directory"). Say I wanted to change my directory to my downloads folder. How I personally would do that is just open my downloads folder in my file explorer, then click and copy the directory at the top, then go to my command prompt and type cd, then I'd paste the directory I copied. So to change my directory to my downloads folder, I'd basically be typing:

<br>

`cd C:\Users\Jaspev\Downloads`

<br>

Say you wanted to download to a diffrent drive. You can't cd between drives. You need to specifically type the name of the drive first, press enter, then you'd be in that new drive and you could cd anywhere in that drive after that. So if I wanted to go to my E: drive's "downloads" folder, I'd first type "E:" then press enter. Then I'd type:

<br>

`cd E:\Downloads`

<br>

Now we can finally start downloading something. To download something with yt-dlp you simply just type "yt-dlp" followed by the link to whatever you want to download. So if I want to download [this](https://youtu.be/jNQXAC9IVRw) amazing video from YouTube, I just type:

<br>

`yt-dlp https://youtu.be/jNQXAC9IVRw`

<br>

But you can see why doing all this would be pretty annoying though, even if you do remember exactly what to type to get to your downloads directory (or whatever directory you want to download to), it still takes a decent amount of time, and the whole point of using yt-dlp is to be quicker than going to a website and using that. But luckily yt-dlp lets you have a config file that automatically changes certain settings every time you run a yt-dlp command, and one of those settings can change the default download location of everything we download!

<br>

## Changing the default downloads location:

<br>

We need to first find where to put our config. You need to put your config in your roaming appdata folder, specifically in a folder called "yt-dlp". To find your roaming appdata folder, lets use the command prompt again, :) just cause we have it open. All you need to type is:

<br>

`start %appdata%`

<br>

And it should open your appdata folder. In that folder make a new folder, titled "yt-dlp" (if it doesn't already exist). And in that yt-dlp folder, make a new file just titled "config". This file shouldn't be a text file, it shouldn't be any type of file, it should have no file extension. To edit this file, I would double click it and Windows should give you a pop-up asking what program you want to open it with. I'd just click any text editor you want to use, like notepad. After you have this open in notepad, type "-o" followed by whatever directory you want your downloads to go to, then after that, you need to tell yt-dlp what the name of the downloaded file is going to be called. All of this will be in quotations, aside from the "-o". I want mine to download to my normal C drive downloads, and just have the name of whatever the file is titled. So I'll do this:

<br>

<p style="text-align: left;">-o "C:\Users\Jaspev\Downloads\%(title)s.%(ext)s"</p>

<br>

So with that, any time I download a file, it will download to my downloads directory, and it's name will be it's title on YouTube (or wherever I'm downloading from). It will know the title because I did %(title)s. The ".%(ext)s" at the end is the file extension (that part is very important). But that's basically it! Now you can download any video from YouTube, Twitter, TikTok, etc., any song from Soundcloud, Bandcamp, and any content from many other websites. It doesn't work with Spotify though. Spotify has strict DRM, the only known way (as far as I know) is to just directly record Spotify, which is what an application called [Spyify](https://jwallet.github.io/spy-spotify/overview.html) can do for you (I haven't tested it, I've just read about it, use at your own risk).

<br>

## Other miscellaneous things yt-dlp can do:

<br>

Yt-dlp can also do things like convert a YouTube video to audio, or download the thumbnail along with a song from Soundcloud. To convert a YouTube video to audio, you'd just put "-x" and the end of the command. So it would look something like this:

<br>

`yt-dlp (link to whatever vid you're downloading) -x`

<br>

That will export the vid to just whatever audio format. If you want to change the audio format to mp3, you'd do the same thing as above, but add "`--`audio-format mp3" to the end.

<br>

You can also add --write-thumbnail to the end and it'll download the thumbnail/cover to the content you're downloading.

<br>

Yt-dlp has a rediculous amount of different options and stuff you can do with it, you can see the full list on the yt-dlp github [here](https://github.com/yt-dlp/yt-dlp?tab=readme-ov-file#general-options).

<br>

## Recap:

<br>

So any time you want to download something like a YouTube video, these are the steps now that you have yt-dlp installed:

<br>

**`1.`** Copy the link to the content you want to download
<br>
**`2.`** Press Win+X
<br>
**`3.`** When the window in the bottom left opens up, press A and the command prompt should open up.
<br>
**`4.`** In the command prompt type yt-dlp and paste the link you copied, then press enter, and it should download to wherever you set your download directory in the config file.

<br>

Thank you for reading, I hope this tutorial worked for you! :)