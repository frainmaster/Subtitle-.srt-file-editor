# Subtitle (.srt) File Editor
It is something, by @frainmaster.

NOTE: This program **DOES NOT** create subtitle files. It just **CHANGE THE TIME LAPSE** of the subtitles so that it can
get along with the dialogues accordingly.

SRT file is a subtitle file for video. It can be included in a video player when a user play some video and drag the subtitle file into the video player. It can be opened and read with a text document file.

The format of a subtitle file is:
* number of dialogue/subtitle
* time frame (in format of time in hour, minute, second and millisecond followed by dash (`-->`) and the time again)
* subtitle line

![](https://github.com/frainmaster/Subtitle-.srt-file-editor/blob/master/sub.PNG)

The subtitle files also follow formatting rules (such as what's in the picture) to customize the subtitles to be bold, italic and even with different colours and fonts.

> Basically, what this program does is it changes the time frame part of every single subtitles. You can edit it manually: you can change every single time frame by typing with your own hands but in average, 2 hours-long movie has an average of 2000 dialogues. And normally, the problem with subtitle files online are that they vary by few seconds from original dialogue, and every dialogue varies at the same rate.

#
### Program

1. The program will need the path for the subtitle file, so the first user input will be the path of the containing folder.

![](https://github.com/frainmaster/Subtitle-.srt-file-editor/blob/master/1.PNG)

TIP: The path of the folder can be taken from the properties of the text file itself or clicking the path box (*I mean, if you are a programmer you should know how things works*)

![](https://github.com/frainmaster/Subtitle-.srt-file-editor/blob/master/2.PNG)

2. The program will then ask for the name of the text file. Copy and paste it. Don't forget the file extension (`.srt`)

> At this point, the program will combine both file path and the name of the text file into a variable and change all the backslashes (`\`) to normal slash (`/`) because that's how reading file in python works. It will then print the whole string as a confirmation.

![](https://github.com/frainmaster/Subtitle-.srt-file-editor/blob/master/3.PNG)

3. Then, it will ask for the name of the new file. You don't have to include extension (`.srt`) as it will create a text file with extension `.srt` right away.
![](https://github.com/frainmaster/Subtitle-.srt-file-editor/blob/master/4.PNG)

4. Lastly, the program will ask for the amount of time user want the timer to be increased. By putting a positive number, it will make the subtitle file late by the amount of time you want; while if you put a negateive number it will make the timer early.
> For the example, I increased the program by 1 second.
> The amount of time you want to increase can be as small as 1 millisecond (0.001 second) since the time format is that accurate.

![](https://github.com/frainmaster/Subtitle-.srt-file-editor/blob/master/5.PNG)

5. After around 2 seconds of running (the program will print all the time frames that it changes, with the new edited time frame), the new text file will be created in the original folder.
> Try comparing the time frame of the new file and the original file. The only part that is changed is the time frame of every subtitles.

![](https://github.com/frainmaster/Subtitle-.srt-file-editor/blob/master/6.PNG)

#
