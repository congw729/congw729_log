# Awesome Paper List of Diffusion Models
This paper list contains papers of awesome diffusion models in vision (image/video generation) area.

Three cornerstone papers of diffusion models:
1. [Deep unsupervised learning using nonequilibrium thermodynamics](http://proceedings.mlr.press/v37/sohl-dickstein15.html) 2015, "Diffusion" occured in machine learning first time
2. **NCSN** [Generative modeling by estimating gradients of the data distribution](https://proceedings.neurips.cc/paper/2019/hash/3001ef257407d5a371a96dcd947c7d93-Abstract.html) 2019, Noice Conditioned Score Network
3. **DDPM** [Denoising diffusion probabilistic models](https://proceedings.neurips.cc/paper/2020/hash/4c5bcfec8584af0d967f1ab10179ca4b-Abstract.html) 2020, could seen as cornerstone of following diffusion model works

[toc]

# Vision
## Image generation
1. **Improved diffusion** [Improved denoising diffusion probabilistic models](https://proceedings.mlr.press/v139/nichol21a.html) Feb 2021, from OpenAI, PMLR 2021.
2. **Guided diffusion** [Diffusion models beat gans on image synthesis](https://proceedings.neurips.cc/paper/2021/hash/49ad23d1ec9fa4bd8d77d02681df5cfa-Abstract.html) Apr 2021, from OpenAI, NeurIPS 2021.
3. ADM, May 2021, from OpenAI, NeurIPS 2021.
4. FastDPM, May 2021, from NVIDIA, ICLR Workshop 2021.
5. LSGM, Jun 2021, from NVIDIA, NeurIPS 2021.
6. Distilled-DM, Feb 2022, from Google Brain, ICLR 2022.
7. GGDM, Feb 2022, from Google Brain, ICLR 2022.

## Text to Image
1. 🌟**Stable Diffusion/LDM** [High-resolution image synthesis with latent diffusion models](https://openaccess.thecvf.com/content/CVPR2022/html/Rombach_High-Resolution_Image_Synthesis_With_Latent_Diffusion_Models_CVPR_2022_paper.html)  Dec 2021, from Stability.AI & LMU Munic & Runway. Very awoesome for releasing codes & weights for free!
2. [**Glide**: Towards photorealistic image generation and editing with text-guided diffusion models](https://arxiv.org/abs/2112.10741) Dec 2021, from OpenAI
3. **Dalle-2** [Hierarchical text-conditional image generation with clip latents](https://arxiv.org/abs/2204.06125) Apr 2022, from OpenAI. Btw, Dalle using different architecture -  VQ-VAE. 
4. [**KNN Diffusion**: Image Generation via Large-Scale Retrieval](https://arxiv.org/abs/2204.02849) Apr 2022, from Meta AI.
5. [**Imagen**:Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding](https://arxiv.org/abs/2205.11487) May 2022,  from Google Brain. Using pretrained languange model - T5.
6. LAION-RDM, Text-Guided Synthesis of Artistic Images with Retrieval-Augmented Diffusion Models, Jul 2022, from Ludwig-Maximilian University of Munich.
7. DreamBooth: Fine Tuning Text-to-Image Diffusion Models for Subject-Driven Generation, Aug 2022, from Google Research & Boston University.
8. [**DreamFusion**: Text-to-3D using 2D Diffusion](https://arxiv.org/abs/2209.14988) 29 Sep 2022, from Google Research & UCB.

## Image Editing
1. SDEdit, Aug 2021, from Stanford University & Carnegie Mellon University, ICLR 2022
2. RePaint, Jan 2022, from ETH Zurich, CVPR 2022.

## Video Genereation: 
1. [**Video diffusion models**](https://arxiv.org/abs/2204.03458), Apr 2022, ICLR 2022 Workshop. GIF like.
2. MCVD: Masked Conditional Video Diffusion for Prediction, Generation, and Interpolation, May 2022, from University of Montreal
3. [**Make-A-Video**: Text-to-Video Generation without Text-Video Data](https://arxiv.org/abs/2209.14792), 29 Sep 2022, from Meta AI (Previous work is Make A Scence, VQ-VAE + classifer free guidence)
4. [**Imagen Video**: High Definition Video Generation with Diffusion Models](https://arxiv.org/abs/2210.02303), 5 Oct 2022, from Google Brain (Also annoced [Phenaki](https://arxiv.org/abs/2210.02399) for long video generation, but it is not diffusion model)

# Natural language:
1. **Diffusion-LM** [Diffusion-LM Improves Controllable Text Generation]

# Audio
## Audio Generation
1. DiffWave, Jun 2020, from UCSD & Nvidia & Baidu, ISMIR 2021
2. WaveGrad, Sep 2020, from Google Brain, ICLR 2021.
3. Symbolic Music Generation, Mar 2021, from Google Brain, ISMIR 2021
4. DiffSinger, May 2021, from Zhejiang University, AAAI 2022
5. VDM, Jul 2021, from Google Brain, NeurIPS 2021.
6. FastDiff, Apr 2022, from Zhejiang University & Tencent AI Lab, IJCAI 2022
7. BDDMs, May 2022, from Tencetn AI Lab, ICLR 2022
8. SawSing, AUG 2022, ISMIR 2022
9. Prodiff, JUL 2022, from Zhejiang University, ACM Muiltimedia 2022

## Audio Conversion
1. DiffVC, Sep 2021, from Huawei Noah, ICLR 2022.

## Audio Enhancement
1. NU-Wave, Apr 2021, from MINDSLAB & Seoul National University, Interspeech 2021
2. CDiffSE, Feb 2022, from CMU & Reality Labs Research, Pittsburgh & Academia Sinica, IEEE 2022

## Text to Speech
1. Grad-TTS, May 2021, from Huawei Noah
2. EdiTTS, Oct 2021, from Yale University & Supertone Inc & Neosapience Inc
3. DiffGAN-TTS, Jan 2022, from Tencent AI Lab
4. Diffsound, Jul 2022, from Beijing University & Tencent AI Lab



🦄 **Some good materials to get start with:**
1. [Lilianweng's Log - What are Diffusion Models?](https://lilianweng.github.io/posts/2021-07-11-diffusion-models)
2. [Youtube@AICofeeBreak - "diffusion" related videos](https://www.youtube.com/c/AICoffeeBreak/search?query=diffusion)
3. [Bilibili@deep_thoughts - DDPM algorithm and its codes, video explained (Chinese)](https://www.bilibili.com/video/BV1b541197HX/?spm_id_from=333.337.search-card.all.click&vd_source=12957bc7127f3a408af0ba8928de89b3)


👾 Personal slides:
1. [Google Slides - Intro to diffusion models](https://docs.google.com/presentation/d/e/2PACX-1vSBq6Mio9NvmAk8snqwxlcAUlVABrJYg8L5itf6AxK6k1MoFEYjXY2b-NVLyG2mu8Ae77p-GhhjLRFw/pub?start=false&loop=false&delayms=3000)
