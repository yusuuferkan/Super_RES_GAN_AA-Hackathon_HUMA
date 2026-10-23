<div align="center">

# 🔍 Super-Resolution with Real-ESRGAN

**Hackathon project: upscaling low-resolution images and videos ×2 / ×4 with a GAN, on a GPU or a plain laptop.**

![Python](https://img.shields.io/badge/Python-3-3776AB?logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![Real-ESRGAN](https://img.shields.io/badge/model-Real--ESRGAN-8A2BE2)
![Colab](https://img.shields.io/badge/Google%20Colab-ready-F9AB00?logo=googlecolab&logoColor=white)
![Hackathon](https://img.shields.io/badge/HUMA-Hackathon-ff69b4)

</div>

---

## 🎯 About

Built for the **HUMA Hackathon** (August 2024). The pipeline uses **[Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN)**, a GAN trained on synthetic real-world degradations (blur, noise, JPEG artifacts), to restore and upscale:

- 🖼️ **Images:** ×2 / ×4 upscaling, with optional face enhancement through GFPGAN
- 🎞️ **Videos:** frame-by-frame upscaling with `realesr-animevideov3`
- 💻 **No-CUDA option:** portable NCNN-Vulkan binaries that run on Intel, AMD and NVIDIA GPUs without CUDA or PyTorch

## 🚀 Quickstart

### Option A: Python / Colab

This repo holds the hackathon's inference, setup and deployment scripts. The `realesrgan` package itself comes from upstream:

```bash
git clone https://github.com/xinntao/Real-ESRGAN.git
cd Real-ESRGAN
pip install basicsr facexlib gfpgan ffmpeg-python
pip install -r requirements.txt
python setup.py develop
```

**Image:**

```bash
python inference_realesrgan.py -n RealESRGAN_x4plus -i inputs/ -o results/ --face_enhance
```

**Video:**

```bash
python inference_realesrgan_video.py -i inputs/video/my_video.mp4 -n realesr-animevideov3 -s 2 --suffix outx2
```

In Colab, download the result with `files.download('results/my_video_outx2.mp4')`.

### Option B: portable executable (no Python)

Download for [Windows](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.5.0/realesrgan-ncnn-vulkan-20220424-windows.zip) · [Linux](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.5.0/realesrgan-ncnn-vulkan-20220424-ubuntu.zip) · [macOS](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.5.0/realesrgan-ncnn-vulkan-20220424-macos.zip), then run:

```bash
./realesrgan-ncnn-vulkan -i input.jpg -o output.png -n realesrgan-x4plus
```

## 🧠 Models

| Model | Best for |
|---|---|
| `realesrgan-x4plus` *(default)* | General photos, ×4 |
| `realesrnet-x4plus` | Smoother output, fewer GAN artifacts |
| `realesrgan-x4plus-anime` | Anime and illustrations (small model) |
| `realesr-animevideov3` | Animation video |

## 📁 Files

| File | Purpose |
|---|---|
| `inference_realesrgan.py` | Image inference CLI |
| `inference_realesrgan_video.py` | Video inference CLI |
| `cog_predict.py`, `cog.yaml` | Deployment with [Cog](https://github.com/replicate/cog) / Replicate |
| `setup.py`, `requirements.txt` | Installation |

## 🙏 Credits

Built on **Real-ESRGAN** by Xintao Wang et al.:
[*Real-ESRGAN: Training Real-World Blind Super-Resolution with Pure Synthetic Data*](https://arxiv.org/abs/2107.10833), ICCVW 2021. The upstream code is BSD-3-Clause licensed.

---

<div align="center">

Made by **[Yusuf Erkan](https://www.linkedin.com/in/yusuferkan1/)** · ⭐ Star it if it helped you

</div>
