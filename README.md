# PALLAIDIUM - Generative AI for the Blender VSE
AI-generate video, image, and audio from text prompts or video, image, or text strips. 

![PallAIdium](https://github.com/tin2tin/Generative_AI/assets/1322593/1b1b232f-00d9-4b0b-86fb-5f0f24136d2c)

## Features

|                                                    |                                                     |
|----------------------------------------------------|-----------------------------------------------------|
| Text to video                                      | Text to audio                                       |
| Text to speech                                     | Text to image                                      |
| Image to image                                     | Image to video                                     |
| Video to video                                     | Style selector                                     |
| ControlNet                                         | OpenPose                                          |
| Canny                                          | Illusion                                          |
| Seed                                               | Quality steps                                     |
| Frames                                             | Word power                                         |
| Denoising                                          | Strip power                                        |
| Batch conversion                                   | Batch refinement of images.                         |
| Batch upscale & refinement of movies.              | Model card selector.                               |
| Render-to-path selector.                          | Render finished notification.                      |
| Model Cards                                       | One-click install and uninstall dependencies. |
| User-defined file path for generated files.        | Define the location for storing generated files.  |
| Seed and prompt added to strip name.             | Include seed and prompt information in the strip name. |


![image](https://github.com/tin2tin/Pallaidium/assets/1322593/09bba394-3188-49be-8ae1-37c0c43ec2fd)

## Requirements
* Windows or Linux (Could maybe work on MacOS, but someone will have to contribute code to make it work).
* A CUDA-supported Nvidia card with at least 4 GB VRAM.
  

## How to install
(As for Linux, if anything differs in installation, then please share instructions.)

* First you must download and install git for your platform(must be on PATH(or Bark will fail)): https://git-scm.com/downloads

* Download the add-on: https://github.com/tin2tin/text_to_video/archive/refs/heads/main.zip

* On Windows, right-click on the Blender icon and "Run Blender as Administrator"(or you'll get write permission errors).

* Install the add-on as usual: Preferences > Add-ons > Install > select file > enable the add-on. 

* In the Generative AI add-on preferences, hit the "Install Dependencies" button.

* Note that you can change what model cards are used in the various modes here(video, image, and audio).

* Then it writes that it is finished(if any vital errors, let me know).
  
* Restart Blender.

* Open the add-on UI in the Sequencer > Sidebar > Generative AI.

* The first time any model is executed many GB will have to be downloaded, so go grab lots of coffee. 

* If it says: "ModuleNotFoundError: Refer to https://github.com/facebookresearch/xformers for more information on how to install xformers", then try to restart Blender.

Tip           |
:------------- |
If any Python modules are missing, use this add-on to manually install them:      |
https://github.com/amb/blender_pip      |


## Location

Install Dependencies, set Movie Model Card, and set Sound Notification in the add-on preferences:

![image](https://github.com/tin2tin/Generative_AI/assets/1322593/49ba0182-f8a0-4a1d-b24f-caca9741d033)

Video Sequence Editor > Sidebar > Generative AI:

![image](https://github.com/tin2tin/Generative_AI/assets/1322593/318a4ec2-8d0f-4aaf-8fd8-9131f8b15918)

Styles:

![image](https://github.com/tin2tin/Generative_AI/assets/1322593/86807264-a377-4de1-875e-471aaa3011a7)

See SDXL handling most of the styles here: https://stable-diffusion-art.com/sdxl-styles/


## Updates

Read about the updates here: 

https://github.com/tin2tin/Pallaidium/discussions/categories/announcements


## Text to Video
The Animov models have been trained on Anime material, so adding "anime" to the prompt is necessary, especially for the Animov-512x model. 

## Text to Image
The Stable Diffusion models for generating images have been used a lot, so there are plenty of prompt suggestions out there if you google for them. 

### Artists
https://stablediffusion.fr/artists

### Prompting:
https://github.com/invoke-ai/InvokeAI/blob/main/docs/features/PROMPTS.md

https://stablediffusion.fr/prompts

Tip           |
:------------- |
If the image of your renders breaks, then use the resolution from the Model Card in the Preferences.     |

Tip           |
:------------- |
If the image of your playback stutters, then select a strip > Menu > Strip > Movie Strip > Set Render Size.     |

Tip           |
:------------- |
If you get the message that CUDA is out of memory, then restart Blender to free up memory and make it stable again.     |


# Batch Processing

Select multiple strips and hit Generate. When doing this, the file name, and if found the seed value, are automatically inserted into the prompt and seed value. However in the add-on preferences this behaviour can be switched off.

https://github.com/tin2tin/Pallaidium/assets/1322593/28098eb6-3a93-4bcb-bd6f-53b71faabd8d

# Text to Audio

### Bark
Find Bark documentation here: https://github.com/suno-ai/bark
* [laughter]
* [laughs]
* [sighs]
* [music]
* [gasps]
* [clears throat]
* — or ... for hesitations
* ♪ for song lyrics
* capitalization for emphasis on a word
* MAN/WOMAN: for bias towards the speaker

Speaker Library: https://suno-ai.notion.site/8b8e8749ed514b0cbf3f699013548683?v=bc67cff786b04b50b3ceb756fd05f68c

Tip           |
:------------- |
If the audio breaks up, try processing longer sentences.      |

### AudioLDM2
Find AudioLDM documentation here: https://github.com/haoheliu/AudioLDM
Try prompts like: Bag pipes playing a funeral dirge, punk rock band playing hardcore song, techno dj playing deep bass house music, and acid house loop with jazz.
Or: Voice of God judging mankind, woman talking about celestial beings, hammer on wood.


## Performance

On 6 GB of VRAM I typically render images first with 1024x512 images with SDXL. And img2vid with Zeroscope XL in 768x384x10 or 640x320x17.

## New to Blender?

Watch this tutorial: https://youtu.be/4_MIaxzjh5Y?feature=shared


## AI Modules
Diffusers: https://github.com/huggingface/diffusers

ModelScope: https://modelscope.cn/models/damo/text-to-video-synthesis/summary

Animov: https://huggingface.co/vdo/animov-0.1.1

Potat1: https://huggingface.co/camenduru/potat1

Zeroscope Dark: https://huggingface.co/cerspense/zeroscope_v2_dark_30x448x256

Zeroscope XL: https://huggingface.co/cerspense/zeroscope_v2_XL

AudioLDM2 Music: [https://huggingface.co/cvssp/audioldm-s-full-v2 https://github.com/haoheliu/AudioLDM](https://huggingface.co/cvssp/audioldm2-music)

Bark: https://github.com/suno-ai/bark

Deep Floyd IF: https://github.com/deep-floyd/IF

Stable Diffusion XL: https://huggingface.co/stabilityai/stable-diffusion-xl-base-0.9



## Uninstall

Hugging Face diffusers model is downloaded from the hub and saved to a local cache directory. By default, the cache directory is located at:

On Linux and macOS: ~/.cache/huggingface/hub

On Windows: %userprofile%\\.cache\huggingface\hub

Here you can locate and delete the individual models.

## Useful add-ons

### Add Rendered Strips

Since the Generative AI add-on only can input image or movie strips, you'll need to convert other strip types to movie-strip. For this purpose, this add-on can be used:

https://github.com/tin2tin/Add_Rendered_Strips

![image](https://github.com/tin2tin/Generative_AI/assets/1322593/d8c0a184-d812-440d-a5a8-501a1282d78d)

### VSE Masking Tools

For creating a mask on top of a clip in the Sequencer, this add-on can be used to input the clip as background in the Blender Image Editor. The created mask can then be added to the VSE as a strip, and converted to video with the above add-on:

https://github.com/tin2tin/vse_masking_tools

![image](https://github.com/tin2tin/Generative_AI/assets/1322593/f2afd36c-34b1-4779-957b-0eb8defed296)



## Video Examples
### Zeroscope & Bark:
[![Watch the video](https://img.youtube.com/vi/LejSJGmtEvE/0.jpg)](https://youtu.be/LejSJGmtEvE) [![Watch the video](https://img.youtube.com/vi/AAdQfQjENJU/0.jpg)](https://youtu.be/AAdQfQjENJU) 

### Video to video:

https://github.com/tin2tin/Generative_AI/assets/1322593/c044a0b0-95c2-4b54-af0b-45bc0c670c89

https://github.com/tin2tin/Generative_AI/assets/1322593/0105cd35-b3b2-49cf-91c1-0633dd484177

### Img2img:
https://github.com/tin2tin/Generative_AI/assets/1322593/2dd2d2f1-a1f6-4562-8116-ffce872b79c3

### Painting
https://github.com/tin2tin/Generative_AI/assets/1322593/7cd69cd0-5842-40f0-b41f-455c77443535


## Restrictions for using the AI models:

- The models can only be used for non-commercial purposes. The models are meant for research purposes.
- The models was not trained to realistically represent people or events, so using it to generate such content is beyond the model's capabilities.
- It is prohibited to generate content that is demeaning or harmful to people or their environment, culture, religion, etc.
- Prohibited for pornographic, violent, and bloody content generation.
- Prohibited for error and false information generation.








