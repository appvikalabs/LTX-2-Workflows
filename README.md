---
tags:
- ltx
- ltx-2
- comfyui
- comfy
- GGUF
- ltx-video
---

The workflows are based on the extracted models from https://huggingface.co/Kijai/LTXV2_comfy 
The extracted models runs easier on the computer (as separate files), as well as GGUF support etc

(but you can easily swap out the model loader for the ComfyUI default model loader if you want to load the checkpoint with "all in one" vae built-in etc) 


Gemma 3 12B it GGUF text encoder:
https://huggingface.co/unsloth/gemma-3-12b-it-GGUF/

Needed nodes:

https://github.com/kijai/ComfyUI-KJNodes

https://github.com/city96/ComfyUI-GGUF   


<video src="https://cdn-uploads.huggingface.co/production/uploads/64afc36a09727d75e9ca79aa/442uH7jw-TrAfxGs5TU_9.mp4" controls autoplay loop muted width="100%"></video>

(video credit to https://www.reddit.com/user/fantazart/)



-- -- 


More workflows:

ComfyUI official workflows: https://docs.comfy.org/tutorials/video/ltx/ltx-2 

LTX-Video official workflows:  https://github.com/Lightricks/ComfyUI-LTXVideo/tree/master/example_workflows  


RunComfy (can download workflow to use locally): 

LTX-2 Controlnet (pose, depth etc)  https://www.runcomfy.com/comfyui-workflows/ltx-2-controlnet-in-comfyui-depth-controlled-video-workflow 

LTX-2 First Last Frame  https://www.runcomfy.com/comfyui-workflows/ltx-2-first-last-frame-in-comfyui-audio-visual-motion-control