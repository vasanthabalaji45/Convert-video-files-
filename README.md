# Convert-video-files-
Convert video files in linux using  ffmpeg <br>
<br>
:pick: convert a video file from onre format to other <br>
<br>
:toolbox:ffmped <br>

To convert a .mov file to mp4 using ffmpeg, you can use the following command:

Install Git. If Git is not already installed on your system, you can install it using your system's package manager. For example, on a Debian-based system (such as Ubuntu), you can use the following command:

:red_circle:sudo apt-get install git
On a CentOS system, you can use the following command:

:red_circle:sudo yum install git

Clone the repository. To clone the repository, use the git clone command followed by the URL of the repository you want to clone.

:red_circle:git clone https://git.ffmpeg.org/ffmpeg.git ffmpeg

ffmpeg -i input.mov -c:v libx264 -c:a aac -strict experimental output.mp4
This command will convert the input.mov file to an output.mp4 file. The -c:v option specifies the video codec to use, and the -c:a option specifies the audio codec to use. The -strict experimental option is required because the aac codec is considered experimental.

You can also use the following command to specify the desired bitrate for the output file:

:red_circle:ffmpeg -i input.mov -c:v libx264 -b:v 500k -c:a aac -strict experimental output.mp4
This command will create an output.mp4 file with a video bitrate of 500 kbps.

To write a script to automate this process, you can use a shell script, Python script, or any other scripting language of your choice. Here is an example of a shell script that converts all .mov files in the current directory to mp4:
:red_circle:
#!/bin/bash<br>
<br>
for file in *.mov; do<br>
  ffmpeg -i "$file" -c:v libx264 -c:a aac -strict experimental "${file%.*}.mp4"<br>
done<br>
To use this script, save it to a file (e.g., convert.sh) and make it executable using the chmod command:<br>
<br>
:round_pushpin:chmod +x convert.sh<br>
You can then run the script using the following command:<br>
<br>
:round_pushpin:./convert.sh<br>
This script will convert all .mov files in the current directory to mp4 files.<br>
