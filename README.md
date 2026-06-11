<span>📚English  |   <a href="./README_CN.md">📚中文阅读 </a> &nbsp;  | &nbsp; <a href="https://mp.weixin.qq.com/s/o6MMOzbmGBRpB_a_9U8JMw?">机器之心</a> &nbsp;  | &nbsp; <a href="https://mp.weixin.qq.com/s/X9ql9U3-OijymvUQNaOBQw">百度文心</a> 
</span>


<div align="center">
<img src="https://unicomai.github.io/LeMiCa/static/images/logv2.png" style="width:auto; height:150px;">
</div>



# [NeurIPS 2025 Spotlight] LeMiCa: Lexicographic Minimax Path Caching for Efficient Diffusion-Based Video Generation

<div class="is-size-5 publication-authors" align="center">
  <span class="author-block">
    <a href="https://github.com/joelulu" target="_blank">Huanlin Gao</a><sup>1,2</sup><sup>*</sup>,&nbsp;
  </span>
  <span class="author-block">
    <a href="https://scholar.google.com/citations?hl=zh-CN&view_op=list_works&user=gpNOW2UAAAAJ" target="_blank">Ping Chen</a><sup>1,2</sup><sup>*</sup>,&nbsp;
  </span>
  <span class="author-block">
    <a href="https://github.com/stone002" target="_blank">Fuyuan Shi</a><sup>1,2</sup>,&nbsp;
  </span>
  <span class="author-block">
    <a href="https://github.com/tanchaow" target="_blank">Chao Tan</a><sup>1,2</sup>,&nbsp;
  </span>
  <span class="author-block">
    <a href="https://scholar.google.com/citations?hl=en&user=L4OXOs0AAAAJ" target="_blank">Zhaoxiang Liu</a><sup>1,2</sup>
  </span>
  <br>
  <span class="author-block">
    <a href="https://github.com/FangGet" target="_blank">Fang Zhao</a><sup>1,2</sup><sup>†</sup>,&nbsp;
  </span>
  <span class="author-block">
    <a href="https://scholar.google.com/citations?user=CFUQLCAAAAAJ&hl=en" target="_blank">Kai Wang</a><sup>1,2</sup>,&nbsp;
  </span>
  <span class="author-block">
    <a href="https://scholar.google.com.hk/citations?user=kCC2oKwAAAAJ&hl=zh-CN&oi=ao" target="_blank">Shiguo Lian</a><sup>1,2</sup><sup>†</sup>
  </span>
</div>

<div class="is-size-5 publication-authors" align="center">
  <span class="author-block"><sup>1</sup>Data Science & Artificial Intelligence Research Institute, China Unicom,&nbsp;</span>
  <span class="author-block"><sup>2</sup>Unicom Data Intelligence, China Unicom</span>
</div>

<div class="is-size-5 publication-authors" align="center">
  (* Equal contribution. † Corresponding author.)
</div>

<h5 align="center">

<a href="https://unicomai.github.io/LeMiCa/" target="_blank">
  <img src="https://img.shields.io/badge/Project-Website-blue.svg" alt="Project Page">
</a>
<!-- <a href="https://github.com/UnicomAI/LeMiCa" target="_blank">
  <img src="https://img.shields.io/badge/Code-GitHub-black.svg?logo=github" alt="Code">
</a> -->
<a href="https://arxiv.org/abs/2511.00090" target="_blank">
  <img src="https://img.shields.io/badge/Paper-PDF-critical.svg?logo=adobeacrobatreader" alt="Paper">
</a>
<!-- <a href="https://github.com/UnicomAI/LeMiCa/raw/main/assets/LeMiCa_NeurIPS2025_appendix.pdf" target="_blank">
  <img src="https://img.shields.io/badge/Appendix-PDF-green.svg?logo=file-pdf" alt="Appendix PDF">
</a> -->
</a>
<a href="./LICENSE" target="_blank">
  <img src="https://img.shields.io/badge/License-Apache%202.0-yellow.svg" alt="License">
</a>
<a href="https://github.com/UnicomAI/LeMiCa/stargazers" target="_blank">
  <img src="https://img.shields.io/github/stars/UnicomAI/LeMiCa.svg?style=social" alt="GitHub Stars">
</a>

</h5>


![LeMiCa Overview](./assets/1_overview_clip.jpg)



## Introduction

**LeMiCa** is a training-free acceleration framework for diffusion-based video generation (and extendable to image generation). Instead of using local heuristic thresholds, LeMiCa formulates cache scheduling as a global path optimization problem with error-weighted edges and introduces a Lexicographic Minimax strategy to bound the worst-case global error. This global planning improves both inference speed and consistency across frames. For more details and visual results, please visit our [project page](https://unicomai.github.io/LeMiCa/).



## 🔥 Latest News
- [2026/04/16] ✨ Support [**ERNIE-Image**](https://github.com/UnicomAI/LeMiCa/tree/main/LeMiCa4ErnieImage) text-to-image acceleration with LeMiCa.
- [2026/01/29] 🔥 Our latest work "MeanCache: From Instantaneous to Average Velocity for Accelerating Flow Matching Inference" is accepted by ICLR 2026! Codes are available at [**MeanCache**](https://github.com/UnicomAI/MeanCache)! MeanCache achieves 4.12×, 4.56×, and 3.59× acceleration on FLUX.1, Qwen-Image, and HunyuanVideo, while consistently outperforming state-of-the-art caching baselines in generation quality. For more details, please refer to our latest research paper. 
- [2026/01/20] 🔥 Added support for FLUX.1-dev and FLUX.2-Klein in [**LeMiCa4FLUX**](https://github.com/UnicomAI/LeMiCa/tree/main/LeMiCa4FLUX)
- [2025/12/15] ✨ [**ComfyUI-LeMiCa**](https://github.com/UnicomAI/LeMiCa/tree/main/ComfyUI-LeMiCa) has been seamlessly integrated into [**ComfyUI**](https://github.com/comfyanonymous/ComfyUI) and is fully compatible with ComfyUI’s native nodes.
- [2025/12/08] ✨ Support [**HunyuanVideo-1.5**](https://github.com/UnicomAI/LeMiCa/tree/main/LeMiCa4HunyuanVideo1.5) for both T2V and I2V.
- [2025/12/02] ✨ Support [**Z-Image**](https://github.com/UnicomAI/LeMiCa/tree/main/LeMiCa4Z-Image) and [**FLUX.2**](https://github.com/UnicomAI/LeMiCa/tree/main/LeMiCa4FLUX).
- [2025/11/14] ⭐ We have open-sourced [**Awesome-Acceleration-GenAI**](https://github.com/joelulu/Awesome-Acceleration-GenAI), collecting the latest generation acceleration techniques. Feel free to check it out !
- [2025/11/13] ✨ Support [**Wan2.1**](https://github.com/UnicomAI/LeMiCa/tree/main/LeMiCa4Wan2.1) for both T2V and I2V. 
- [2025/11/07] ✨ Support [**Qwen-Image**](https://github.com/UnicomAI/LeMiCa/tree/main/LeMiCa4QwenImage) and Inference Code Released !  
- [2025/10/29] 🚀 Code will be released soon !  
- [2025/09/18] ✨ Selected as a **NeurIPS 2025 Spotlight** paper.  
- [2025/09/18] ✨ Initial public release of LeMiCa. 

<!-- - [2025/10/20] 🔥 **Qwen-Image** (Text-to-Image) support added.   -->

##  Demo

### ComfyUI-LeMiCa
<p align="center">
  <img src="ComfyUI-LeMiCa\assets\ComfyUI.png" alt="ComfyUI-LeMiCa Workflow" width="850"/>
</p>


### ERNIE-Image

| Method   | ERNIE-Image | LeMiCa-slow | LeMiCa-medium | LeMiCa-fast |
|:-------:|:-----------:|:-----------:|:-------------:|:-----------:|
| **Latency** | 32.168 s | 16.471 s | 11.432 s | 7.043 s |
| **T2I** | <img width="160" alt="ERNIE-Image" src="https://github.com/user-attachments/assets/8249ed77-4c7c-41cc-989d-61a595846899" /> | <img width="160" alt="LeMiCa-slow" src="https://github.com/user-attachments/assets/25ef5d70-aae9-4664-8e95-59ad5848cb6b" /> | <img width="160" alt="LeMiCa-medium" src="https://github.com/user-attachments/assets/17cf4dfb-4d46-4b87-a8ca-7990064b9252" /> | <img width="160" alt="LeMiCa-fast" src="https://github.com/user-attachments/assets/5790d160-66fe-46a7-a8c4-14c66c6f7888" /> |


### FLUX.2 [Klein-9B]

| Method              | Flux.2(klein-9B) | LeMiCa-slow         | LeMiCa-medium    | LeMiCa-fast | LeMiCa-ultra   |
|:-------------------:|:--------------------:|:--------------:|:--------------:|:-------------:|:-------------:|
| **Latency**   | 20.04 s                | 10.77 s          | 8.45 s          | 6.54 s         | 4.59 s          |
| **T2I** | <img width="120" alt="Flux.2(klein-9B)" src="https://github.com/user-attachments/assets/07989284-1856-44c8-8a6b-2b46d9532ff2" /> | <img width="120" alt="LeMiCa-slow" src="https://github.com/user-attachments/assets/66130c70-12e3-479f-9062-55c249128821" /> | <img width="120" alt="LeMiCa-medium" src="https://github.com/user-attachments/assets/445cd63a-a896-4bfa-8705-a1043ed42bef" /> | <img width="120" alt="LeMiCa-fast" src="https://github.com/user-attachments/assets/042f45c6-e9ac-4b60-a6a4-ec7fc603f6e3" /> | <img width="120" alt="LeMiCa-ultra" src="https://github.com/user-attachments/assets/c9356da6-924f-4502-b0e4-a902820f7740" /> |


### Qwen-Image-2512

| Method   | Qwen-Image-2512 | LeMiCa-slow | LeMiCa-medium | LeMiCa-fast |
|:-------:|:-------:|:-----------:|:-------------:|:-----------:|
| **Latency** | 32.8 s  | 18.83 s      | 14.35 s        | 10.41 s      |
| **T2I** | <img width="160" alt="Qwen-Image-2512" src="https://github.com/user-attachments/assets/ae47f0c2-e687-4fc8-bf78-8f9d968feda5" /> | <img width="160" alt="LeMiCa-slow" src="https://github.com/user-attachments/assets/9cc9c647-6650-4294-b8fd-6263c74e20b5" /> | <img width="160" alt="LeMiCa-medium" src="https://github.com/user-attachments/assets/0ff53c58-e1be-4e4f-9574-c6e60cf4e342" /> | <img width="160" alt="LeMiCa-fast" src="https://github.com/user-attachments/assets/220e85ea-17e7-4d86-b9cc-6fdb62049d62" /> |

### HunyuanVideo1.5

#### T2V 720P (Up to a 2.86× speedup）

https://github.com/user-attachments/assets/ebed2e0f-87f4-408e-98e3-93bd29bbc99f

####  I2V 720P (Up to a 3.88× speedup）

https://github.com/user-attachments/assets/d1a83d45-579f-4174-9477-ba0b9aebb322


### FLUX.2
| Method              | Flux.2(cpu-offload) | Flux.2         | LeMiCa-slow    | LeMiCa-medium | LeMiCa-fast   |
|:-------------------:|:--------------------:|:--------------:|:--------------:|:-------------:|:-------------:|
| **Latency**   | 101.2 s                | 32.70 s          | 13.41 s          | 10.20 s         | 6.99 s          |
| **T2I** | <img width="120" alt="Flux2 CPU-offload" src="https://github.com/user-attachments/assets/76fda91e-8819-4914-87e4-8a832135da0f" /> | <img width="120" alt="Flux2" src="https://github.com/user-attachments/assets/a3f320e3-9d36-4618-9953-f714646e6bf7" /> | <img width="120" alt="LeMiCa-slow" src="https://github.com/user-attachments/assets/b28fdd2b-8178-4ba7-bf23-3da66f555593" /> | <img width="120" alt="LeMiCa-medium" src="https://github.com/user-attachments/assets/72b4361d-8afe-4c94-9654-77697e3c1444" /> | <img width="120" alt="LeMiCa-fast" src="https://github.com/user-attachments/assets/56ea6af3-e1a5-4134-890b-24f5666081e9" /> |


### Z-Image
| Method   | Z-Image | LeMiCa-slow | LeMiCa-medium | LeMiCa-fast |
|:-------:|:-------:|:-----------:|:-------------:|:-----------:|
| **Latency**   | 2.55 s  | 2.19 s      | 1.94 s        | 1.78 s      |
| **T2I** | <img width="120" alt="Z-Image" src="https://github.com/user-attachments/assets/e7aa76a9-2ffd-4cfc-8c9d-2240f357850b" /> | <img width="120" alt="LeMiCa-slow" src="https://github.com/user-attachments/assets/e7ff50b9-44bb-48ff-86f9-14dacc1b5144" /> | <img width="120" alt="LeMiCa-medium" src="https://github.com/user-attachments/assets/786ad801-ac92-4467-86a6-661b5e7dca53" /> | <img width="120" alt="LeMiCa-fast" src="https://github.com/user-attachments/assets/722d79b1-69fb-4683-914f-e92533394393" /> |


### Wan2.1

https://github.com/user-attachments/assets/3d99b959-7253-47ec-af0a-da13a66e6d49


### Open-Sora

<details>
  <summary>Click to expand Open-Sora example</summary>

https://github.com/user-attachments/assets/ba205856-2d77-494a-aaa9-09189ba2915c
</details>


### Qwen-Image

<details>
  <summary>Click to expand Qwen-Image example</summary>

<div style="width:85%;max-width:1000px;margin:0 auto;">
  <!-- 图片：无边框，宽度与上面表头一致 -->
  <img
    src="./assets/qw-image.jpg"
    alt="Qwen-Image visual result"
    style="width:100%;height:auto;display:block;margin:10px auto 4px auto;"
  />
</div>

</details>


##  Supported Models
LeMiCa currently supports and has been tested on the following diffusion-based models:  

**Text-to-Video**
- [Open-Sora](https://github.com/hpcaitech/Open-Sora)  
- [Latte](https://github.com/Vchitect/Latte)  
- [CogVideoX 1.5](https://github.com/THUDM/CogVideo)  
- [Wan2.1](https://github.com/Wan-Video/Wan2.1)  
- [HunyuanVideo-1.5](https://github.com/Tencent-Hunyuan/HunyuanVideo-1.5)

**Text-to-Image**
- [ERNIE-Image](https://github.com/PaddlePaddle/ERNIE)  
- [Qwen-Image](https://github.com/QwenLM/Qwen-Image)  
- [Z-Image](https://github.com/Tongyi-MAI/Z-Image)  
- [FLUX.2](https://github.com/black-forest-labs/flux2)  


## ToDo List
- 🗹 Public Project Page  
- 🗹 Paper Released  
- 🗹 Text-to-Image Forward Inference  
- 🗹 Text-to-Video Forward Inference  
- ☐ DAG Construction Code  
- ☐ Support Acceleration Framework   



## Community Contributions & Friendly Links

- [Qwen-Image](https://github.com/QwenLM/Qwen-Image) and [CogVideo](https://github.com/THUDM/CogVideo) featured LeMiCa on their project homepages.

- [Cache-DiT](https://github.com/vipshop/cache-dit) A unified and flexible inference engine for DiTs, integrating and applying LeMiCa’s core insights. Welcome to try and explore. [Details](https://github.com/vipshop/cache-dit/blob/main/docs/User_Guide.md#steps-mask)

- [ComfyUI-LeMiCa](https://github.com/UnicomAI/LeMiCa/tree/main/ComfyUI-LeMiCa) now includes **Z-Image** nodes. Thanks @[scruffynerf](https://github.com/scruffynerf).


## Acknowledgement
This repository is built based on or inspired by the following open-source projects:  [Diffusers](https://github.com/huggingface/diffusers), [TeaCache](https://github.com/ali-vilab/TeaCache), [VideoSys](https://github.com/NUS-HPC-AI-Lab/VideoSys).
We sincerely thank these communities for their open contributions and inspiration.



## License
The majority of this project is released under the **Apache 2.0 license** as found in the [LICENSE](./LICENSE) file.



## 📖 Citation
If you find **LeMiCa** useful in your research or applications, please consider giving us a star ⭐ and citing it by the following BibTeX entry:



```bibtex
@inproceedings{gao2025lemica,
  title     = {LeMiCa: Lexicographic Minimax Path Caching for Efficient Diffusion-Based Video Generation},
  author    = {Huanlin Gao and Ping Chen and Fuyuan Shi and Chao Tan and Zhaoxiang Liu and Fang Zhao and Kai Wang and Shiguo Lian},
  journal   = {Advances in Neural Information Processing Systems (NeurIPS)},
  year      = {2025},
  url       = {https://arxiv.org/abs/2511.00090}
}
```

## ⭐ Star History

<div align='center'>
<a href="https://star-history.com/#UnicomAI/LeMiCa&Date">
  <picture align='center'>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=UnicomAI/LeMiCa&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=UnicomAI/LeMiCa&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=UnicomAI/LeMiCa&type=Date" width=400px />
  </picture>
</a>
</div>
