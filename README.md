# Super-RES-Huma-Projesi

# Kurulum

1.Dosya konumu belirleme

    ```bash
    git clone https://github.com/xinntao/Real-ESRGAN.git
    cd Real-ESRGAN
    ```
1. Bagimli paketleri yukleme

    ```bash
    # Install basicsr - https://github.com/xinntao/BasicSR
    # We use BasicSR for both training and inference
    pip install basicsr
    # facexlib and gfpgan are for face enhancement
    pip install facexlib
    pip install gfpgan
    pip install -r requirements.txt
    python setup.py develop
    ```

---


### Taşınabilir yürütülebilir dosyalar (NCNN)

Indirme linkleri: [Windows](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.5.0/realesrgan-ncnn-vulkan-20220424-windows.zip) / [Linux](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.5.0/realesrgan-ncnn-vulkan-20220424-ubuntu.zip) / [MacOS](https://github.com/xinntao/Real-ESRGAN/releases/download/v0.2.5.0/realesrgan-ncnn-vulkan-20220424-macos.zip) **Intel/AMD/Nvidia GPU için yürütülebilir dosyalar**.

Bu yürütülebilir dosya **taşınabilir** ve gereken tüm ikili dosyaları ve modelleri içerir. CUDA veya PyTorch ortamına gerek yoktur.<br>

Basitçe aşağıdaki komutu çalıştırabilirsiniz (Windows örneği, daha fazla bilgi her yürütülebilir dosyanın README.md dosyasındadır):

```bash
./realesrgan-ncnn-vulkan.exe -i input.jpg -o output.png -n model_name
```
5 model seçeneğimiz vardır:

1. realesrgan-x4plus  (default)
2. realesrnet-x4plus
3. realesrgan-x4plus-anime (optimized for anime images, small model size)
4. realesr-animevideov3 (animation video)

Diğer modeller için `-n` bağımsız değişkenini kullanabilirsiniz; örneğin, `./realesrgan-ncnn-vulkan.exe -i input.jpg -o çıktı.png -n realesrnet-x4plus`

# Real-ESRGAN mimarisini kullanma ve Real-ESRGAN'a giriş yapma 

```bash
!git clone https://github.com/xinntao/Real-ESRGAN.git
%cd Real-ESRGAN
# Ortamı ayarlama
!pip install basicsr
!pip install facexlib
!pip install gfpgan
!pip install ffmpeg-python
!pip install -r requirements.txt
!python setup.py develop
```


#Video ile real-ESRGAN kullanma
```bash
! python inference_realesrgan_video.py -i inputs/video/video_ismi.mp4 -n realesr-animevideov3 -s 2 --suffix outx2
```

# Sonuçları indirme
```bash
files.download('results/video_ismi_outx2.mp4')
```
