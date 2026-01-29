# LTX-2 ComfyUI Workflows

A collection of LTX-2 video generation workflows for ComfyUI, tested on RTX 5090.

## Workflow Status

| # | Workflow | Type | Status | Samples |
|---|----------|------|--------|---------|
| 1 | **I2V Basic** | Image-to-Video | ✅ Working | [8 samples](outputs/i2v/) |
| 2 | **I2V Basic (GGUF)** | Image-to-Video | ⏳ Untested | - |
| 3 | **I2V Basic (custom audio)** | Image-to-Video | ⏳ Untested | - |
| 4 | **I2V Simple (no upscale)** | Image-to-Video | ⏳ Untested | - |
| 5 | **I2V IC-Control (pose)** | Pose Control | ⏳ Untested | - |
| 6 | **T2V Basic** | Text-to-Video | ✅ Working | [5 samples](outputs/t2v/) |
| 7 | **T2V Basic (GGUF)** | Text-to-Video | ⏳ Untested | - |
| 8 | **T2V Basic (low vram)** | Text-to-Video | ⏳ Untested | - |
| 9 | **T2V Basic (custom audio)** | Text-to-Video | ⏳ Untested | - |
| 10 | **First Last Frame** | Keyframe | ✅ Working | [1 sample](outputs/i2v/) |
| 11 | **First Middle Last Frame** | Keyframe | ⏳ Untested | - |
| 12 | **V2V (extend video)** | Video-to-Video | ⏳ Untested | - |
| 13 | **V2A Foley** | Video-to-Audio | ⏳ Untested | - |
| 14 | **IC-Control (All-In-One)** | Multi-Control | ⏳ Untested | - |
| 15 | **I2V Talking Avatar** | Avatar + Audio | ✅ Working | [1 sample](outputs/i2v/talking_avatar_mlk.mp4) |
| 16 | **T2V Talking Avatar** | Avatar + TTS | ⏳ Untested | - |
| 17 | **Beta Sampler Previews** | Experimental | ⏳ Untested | - |

**Legend:** ✅ Working | ⏳ Untested | ❌ Broken | 🔧 Needs Fix

---

## Samples

### I2V (Image-to-Video)

| File | Description |
|------|-------------|
| [LTX-2_00001](outputs/i2v/LTX-2_00001-audio.mp4) | Samurai - Initial animation |
| [LTX-2_00002](outputs/i2v/LTX-2_00002-audio.mp4) | Samurai - With spatial upscaling |
| [LTX-2_00003](outputs/i2v/LTX-2_00003-audio.mp4) | Samurai - Refined prompt |
| [LTX-2_00004](outputs/i2v/LTX-2_00004-audio.mp4) | Samurai - Dragon prompt variation |
| [LTX-2_00008](outputs/i2v/LTX-2_00008-audio.mp4) | Samurai - Katana unsheathing, cherry blossoms |
| [LTX-2_00010](outputs/i2v/LTX-2_00010-audio.mp4) | Samurai→Dragon metamorphosis |
| [LTX-2_00012](outputs/i2v/LTX-2_00012-audio.mp4) | **First-Last Frame**: Samurai→Dragon morph (keyframes) |
| [talking_avatar_mlk](outputs/i2v/talking_avatar_mlk.mp4) | **Talking Avatar**: Face animation with MLK "I Have a Dream" speech |

### T2V (Text-to-Video) - Pure Generation

| File | Prompt |
|------|--------|
| [LTX-2_00005](outputs/t2v/LTX-2_00005-audio.mp4) | Dragon soaring through stormy clouds at sunset, scales shimmering with purple and gold |
| [LTX-2_00006](outputs/t2v/LTX-2_00006-audio.mp4) | Cyberpunk megacity aerial shot at night, holographic ads, flying cars, neon lights |
| [LTX-2_00007](outputs/t2v/LTX-2_00007-audio.mp4) | Deep-sea bioluminescent creatures, glowing jellyfish, translucent fish |
| [LTX-2_00009](outputs/t2v/LTX-2_00009-audio.mp4) | Aurora borealis dancing across Arctic sky, green and purple lights over frozen lake |
| [LTX-2_00011](outputs/t2v/LTX-2_00011-audio.mp4) | Space station orbiting Earth, sunrise over horizon, Milky Way backdrop |

---

## Requirements

### Models (in `ComfyUI/models/`)

```
diffusion_models/
  └── ltx2-19B-FP8-Distilled-step.safetensors (21.6GB)

text_encoders/
  └── gemma-3-12b-it-Q4_K_M.gguf (7.3GB)

clip/
  └── LTX_2_embeddings_connector.safetensors (17MB)

vae/
  └── LTX2_video_vae_bf16_KJ.safetensors (173MB)
  └── ltx2-audio-vae.safetensors (6.5MB)

upscale_models/
  └── LTX2_spatial_upscaler_bf16_KJ.safetensors (159MB)
```

### Custom Nodes

- [ComfyUI-KJNodes](https://github.com/kijai/ComfyUI-KJNodes) - LTX-2 support
- [ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF) - GGUF text encoder loading
- [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite) - Video export
- [ComfyUI-Manager](https://github.com/ltdrdata/ComfyUI-Manager) - Node management

---

## Performance

| Metric | Value |
|--------|-------|
| GPU | NVIDIA GeForce RTX 5090 Laptop GPU |
| Model | LTX-2-19B (distilled fp8) |
| Generation Time | ~110-120 seconds per video |
| Resolution | 768x512 (native) |
| FPS | 24 |
| Duration | 97 frames (~4 seconds) |

---

## File Naming Convention

- `*.mp4` - Video only (no audio)
- `*-audio.mp4` - Video with AI-generated audio
- `*.png` - Preview frame

---

## Resources

- [LTX-2 Official Docs](https://docs.ltx.video/open-source-model/integration-tools/comfy-ui)
- [ComfyUI LTX-2 Tutorial](https://docs.comfy.org/tutorials/video/ltx/ltx-2)
- [Official LTX Workflows](https://github.com/Lightricks/ComfyUI-LTXVideo/tree/master/example_workflows)
- [Model Source](https://huggingface.co/Kijai/LTXV2_comfy)
