# video2mocap ( NOT SUPPORTED )

Convert a video file to animated humanIK skeletons for maya.

**This project never had to intention of being used in a professional capacity 
nor were the results ever anything that can be used in production. Extracting 
skeletal animation from video has moved in a lot since the 4 years this project
was created and are a better source for learning.**

*Updated: 28/12/2022*

<p align="center"><img src="https://github.com/robertjoosten/video2mocap/raw/master/data/thumbnail.png"></p>
<a href="https://vimeo.com/277548081" target="_blank"><p align="center">Click for video</p></a>

## Installation
Clone repository

    git clone https://github.com/robertjoosten/video2mocap.git

In order for this tool to work a couple of 3rd party application will have to
be installed. To make this an easy process bat files are located in the
3rdparty directory and can be used to download/extract and install the
necessary applications.

*   Run 3rdparty/getFFmpeg.bat
    - Download and extract FFmpeg ( 20180630-9f0077c ).

*   Run 3rdparty/getOpenPose.bat
    - Download and extract OpenPose ( 1.3.0 ).
    - Download models for OpenPose

*   Run 3rdparty/getHMR.bat ( Requires python3 + pip3 accessible in PATH )
    - Pull the latest custom fork of the HMR repository.
    - Download models for HMR
    - Pip install requirements.txt

## Usage
From the command line:

    cd video2mocap/
    python video2mocap.py --video_path <VIDEO> --output_dir <OUTPUT>

Available Arguments:

*   **--video_path**: Path to video

*   **--output_dir**: Directory to output the maya files too

*   **--keep_temp**: Keep temp files for debugging ( False by default )

*   **--mayapy_exe**: Overwrite mayapy.exe ( Default requires accessible in PATH )

*   **--python2_exe**: Overwrite python.exe ( Default requires accessible in PATH )

*   **--python3_exe**: Overwrite python3.exe ( Default requires accessible in PATH )

The exe files can be overwritten in case the python interpreters are not
accessible through the PATH variable and a relative path cannot be provided.

## Limitations

*   No camera tracking ( static camera advised )
*   No partial body ( full body in view each frame advised )
*   Limited depth adjustment


## Logs
As loads of things are running in process it is quite simple for something to
go wrong. For this reason a log file is implemented that gets saved into the
output_dir. If the desired result is unexpected these logs can be investigated
to find out what and where something went wrong.

Keypoint matching example:

    2018/07/05/ 12:31:40 | INFO | ---- Match Keypoints Over Multiple Frames ----
    2018/07/05/ 12:31:40 | DEBUG | New Person:            Frame 276
    2018/07/05/ 12:31:40 | DEBUG | Omit Person:           Presence Percentage 0.01

## Versions

*   HMR ( custom fork )
    - Link: https://github.com/robertjoosten/hmr
    - Original Link: https://github.com/akanazawa/hmr

*   OpenPose
    - Version v1.3.0.
    - Link: https://github.com/CMU-Perceptual-Computing-Lab/openpose/releases

*   FFmpeg
    - Version 20180630-9f0077c.
    - Link: https://ffmpeg.zeranoe.com/builds/

*   7Zip
    - Version 18.05.
    - Link: https://www.7-zip.org/download.html

*   Wget:
    - Version wget-1.19.1-win64.
    - Link: https://eternallybored.org/misc/wget/
