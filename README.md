<div align="center">

<h1>Mangio-RVC-Fork (Retrieval-based-Voice-Conversion) </h1>
A fork of an easy-to-use SVC framework based on VITS with top1 retrieval. <br><br>
<b> 

> Please support the original [RVC repository](https://www.bilibili.com/video/BV1pm4y1z7Gm/). Without it, obviously this fork wouldn't have been possible. The Mangio-RVC-Fork aims to essentially enhance the features that the original RVC repo has in my own way. Please note that this fork is NOT STABLE and was forked with the intention of experimentation. Do not use this Fork thinking it is a "better" version of the original repo. Think of it more like another "version" of the original repo.
</b>

[![madewithlove](https://forthebadge.com/images/badges/built-with-love.svg)](https://github.com/liujing04/Retrieval-based-Voice-Conversion-WebUI)
  
[![Licence](https://img.shields.io/github/license/liujing04/Retrieval-based-Voice-Conversion-WebUI?style=for-the-badge)](https://github.com/liujing04/Retrieval-based-Voice-Conversion-WebUI/blob/main/%E4%BD%BF%E7%94%A8%E9%9C%80%E9%81%B5%E5%AE%88%E7%9A%84%E5%8D%8F%E8%AE%AE-LICENSE.txt)
[![Huggingface](https://img.shields.io/badge/🤗%20-Spaces-yellow.svg?style=for-the-badge)](https://huggingface.co/lj1995/VoiceConversionWebUI/tree/main/)

[![Discord](https://img.shields.io/badge/RVC%20Developers-Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/HcsmBBGyVk)

<img src="https://33.media.tumblr.com/2344c05b16d25e60771d315604f90258/tumblr_nmy9cc0Zm71syljkjo1_1280.gif" /><br>
  
</div>

------

> The original RVC [Demo Video](https://www.bilibili.com/video/BV1pm4y1z7Gm/) here!

> Realtime Voice Conversion Software using RVC : [w-okada/voice-changer](https://github.com/w-okada/voice-changer)

> The dataset for the pre-training model uses nearly 50 hours of high quality VCTK open source dataset.

> High quality licensed song datasets will be added to training-set one after another for your use, without worrying about copyright infringement.
# Summary
## Features that this fork (Mangio-RVC-Fork) includes that the original repo doesn't:
+ Local inference with the conv2d 'Half' exception fix. apply the argument --use_gfloat to infer-web.py to use this fix.
+ f0 Inference algorithm overhaul:
  + Added pyworld dio f0 method.
  + Added torchcrepe crepe f0 method.
  + Modifiable crepe_hop_length for the crepe algorithm via the web_gui

## This repository has the following features too:
+ Reduce tone leakage by replacing source feature to training-set feature using top1 retrieval;
+ Easy and fast training, even on relatively poor graphics cards;
+ Training with a small amount of data also obtains relatively good results (>=10min low noise speech recommended);
+ Supporting model fusion to change timbres (using ckpt processing tab->ckpt merge);
+ Easy-to-use Webui interface;
+ Use the UVR5 model to quickly separate vocals and instruments.

# Installing the Dependencies
Using pip (python3.9.8 is stable with this fork)

**Notice**: `faiss 1.7.2` will raise Segmentation Fault: 11 under `MacOS`, please use `pip install faiss-cpu==1.7.0` if you use pip to install it manually.

```bash
pip install -r requirements.txt
```

# Preparation of other Pre-models
RVC requires other pre-models to infer and train.

You need to download them from our [Huggingface space](https://huggingface.co/lj1995/VoiceConversionWebUI/tree/main/).

Here's a list of Pre-models and other files that RVC needs:
```bash
hubert_base.pt

./pretrained 

./uvr5_weights

#If you are using Windows, you may also need this dictionary, skip if FFmpeg is installed
ffmpeg.exe
```
Then use this command to start Webui:
```bash
python infer-web.py
```
If you are using Windows, you can download and extract `RVC-beta.7z` to use RVC directly and use `go-web.bat` to start Webui.

There's also a tutorial on RVC in Chinese and you can check it out if needed.

## Credits
+ [ContentVec](https://github.com/auspicious3000/contentvec/)
+ [VITS](https://github.com/jaywalnut310/vits)
+ [HIFIGAN](https://github.com/jik876/hifi-gan)
+ [Gradio](https://github.com/gradio-app/gradio)
+ [FFmpeg](https://github.com/FFmpeg/FFmpeg)
+ [Ultimate Vocal Remover](https://github.com/Anjok07/ultimatevocalremovergui)
+ [audio-slicer](https://github.com/openvpi/audio-slicer)
## Thanks to all contributors for their efforts

<a href="https://github.com/liujing04/Retrieval-based-Voice-Conversion-WebUI/graphs/contributors" target="_blank">
  <img src="https://contrib.rocks/image?repo=liujing04/Retrieval-based-Voice-Conversion-WebUI" />
</a>

