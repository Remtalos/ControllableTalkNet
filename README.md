# This is a customized version of SortAnons ControllableTalknet
This install has been forked to fix some things for some pals, who were having issues with the original.
Major difference: This baby runs python 3.9 and more importantly CUDA 12.8.1 as well as torch 2.7.0. THIS MEANS BLACKWELL COMPATIBILITY!
Also nice: I added a feature where you can actually organise your input files into a subdirectory. Clean folders are great!

# Controllable TalkNet 
Controllable TalkNet is a web application that lets you synthesize speech, 
which mimics the pitch and pacing of an existing audio clip. It's based on [NVIDIA's implementation](https://github.com/NVIDIA/NeMo)
of TalkNet 2, with some changes to support singing synthesis and higher audio quality.

## Requirements
* A Google account to run Colab, or...
* An NVIDIA GPU with 4+ GB of VRAM
* 10 GB of free space

## How to run
### Google Colab
* [Go to the Colab notebook](https://colab.research.google.com/drive/1aj6Jk8cpRw7SsN3JSYCv57CrR6s0gYPB) and follow the instructions.

### TalkNet Offline (Windows)
# Disclaimer: Since I forked this stuff, you are gonna need my zip too. Sorry, pal.
* [Download the setup script](https://github.com/Remtalos/ControllableTalkNet/releases/latest/download/TalkNetOffline.zip)
and extract it to a folder.
* Run setup.bat. The initial setup will take about 20 minutes.
* When it's done, run talknet.bat to start TalkNet on http://127.0.0.1:8050/. To download updates, run update.bat.

### Docker (Linux)
# I did not test this AT ALL. Never even installed it. Linux makes brain hurt. I did put in different numbers into the dockerfile thingy.
* Install Docker and NVIDIA Container Toolkit.
* [Download the Dockerfile.](https://raw.githubusercontent.com/Remtalos/ControllableTalkNet/main/Dockerfile)
Open a terminal, and navigate to the directory where you saved it.
* Run ```docker build -t talknet-offline .``` to build the image. Add ```sudo``` if you're not using rootless Docker.
* Run ```docker run -it --gpus all -p 8050:8050 talknet-offline``` to start TalkNet on http://127.0.0.1:8050/.
