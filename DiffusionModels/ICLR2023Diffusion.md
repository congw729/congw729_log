# ICLR 2023 Review on Diffusion Related Papers
Click [here](https://docs.google.com/spreadsheets/d/1WwhM-YvEBJnLk45uC_JLv2maA4tFbGwx4UYs9I2sXTY/edit?usp=sharing) to see the full list of diffusion related papers from ICLR 2023.

*Papers are listed by descending order of averaging score*
## DreamFusion
| | |
|--|--|
|Title|Dreamfusion: Text-to-3d using 2d diffusion|
|Paper Link|https://arxiv.org/pdf/2209.14988.pdf |
|Institute |Google Research, UC Berkeley|
| Authors |B Poole, A Jain, JT Barron, B Mildenhall
| Github|Not open source|

![](img/0001.png)
![](img/0002.png)
1. **Task**
	Text-to-3D synthesis
2. **Problem**
	Other works need large-scale datasets and efficient architectures for denoising 3D data
3. **Method**
	Pretrained 2D text-to-image diffusion model to perform text-to-3D synthesis. 
	Introduce a loss based on probability density distillation that enables the use of a 2D diffusion model as a prior for optimization of a parametric image generator.
4. **Performance**
	Our 3D scenes are optimized on a TPUv4 machine with 4 chips. Each chip renders a separate view and evaluates the diffusion U-Net with per-device batch size of 1. We optimize for 15,000 iterations which takes around 1.5 hours. Compute time is split evenly between rendering the NeRF and evaluating the diffusion model.
5. **Dataset**
	Training: requires no 3D training data and no modifications to the image diffusion model
	Evaluation: MS-COCO
6. **Model's information**
	Builds upon mip-NeRF 360.

<details>  
	<summary>Abstract and Bibtex</summary>  
	<p> 
	Recent breakthroughs in text-to-image synthesis have been driven by diffusion models trained on billions of image-text pairs. Adapting this approach to 3D synthesis would require large-scale datasets of labeled 3D data and efficient architectures for denoising 3D data, neither of which currently exist. In this work, we circumvent these limitations by using a pretrained 2D text-to-image diffusion model to perform text-to-3D synthesis. We introduce a loss based on probability density distillation that enables the use of a 2D diffusion model as a prior for optimization of a parametric image generator. Using this loss in a DeepDream-like procedure, we optimize a randomly-initialized 3D model (a Neural Radiance Field, or NeRF) via gradient descent such that its 2D renderings from random angles achieve a low loss. The resulting 3D model of the given text can be viewed from any angle, relit by arbitrary illumination, or composited into any 3D environment. Our approach requires no 3D training data and no modifications to the image diffusion model, demonstrating the effectiveness of pretrained image diffusion models as priors. See dreamfusion3d.github.io for a more immersive view into our 3D results.
	</p> 
	
	@article{poole2022dreamfusion,
	title={Dreamfusion: Text-to-3d using 2d diffusion},
	author={Poole, Ben and Jain, Ajay and Barron, Jonathan T and Mildenhall, Ben},
	journal={arXiv preprint arXiv:2209.14988},
	year={2022}
	}
</details>

## DIFFORMER
| | |
|--|--|
|Title| Geometric Networks Induced by Energy Constrained Diffusion|
|Paper Link|https://openreview.net/pdf?id=j6zUzrapY3L |
|Institute | Anonymous authors|
| Github| Not open source|

![](img/0003.png)
1. **Task**
	Real-word data generation
2. **Problem**
	Complex inter-dependencies among instances involved,  a challenge for uncovering the geometric structures for learning desired instance representation. 
3. **Method**
	 Energy constrained diffusion model - it encodes a batch of instances from a dataset into evolutionary states that progressively incorporate other instances' information by their interactions.
	Propose a new class of neural encoders, Diffusion-based Transformer (DIFFORMER), with two instantiations: a simple version with linear complexity for prohibitive instance numbers, and an advanced version for learning complex structures.
4. **Performance**
	- No exactly training time specified, but DIFFORMER could use Tesla V100 16GB for mini-batch training.
	- Applicable ownstream tasks: semi-supervised node classification, image/text classification, and spatial-temporal dynamics prediction.
5. **Dataset**
	 - For node classification: Cora, Citeseer, Pubmed, Proteins, Pokec.
	 - For image and text classification: STL-10, CIFAR-10.
	 - For spatial-temperoal datasets: Chickenpox, Covid, WikiMath (all from PyTorch Geometric Temporal)
6. **Model's information**
	simple diffusivity model ( $O(NKd^2)$ ) + advanced diffusivity model ( $O(N^2Kd^2)$ )

<details>  
	<summary>Abstract and Bibtex</summary>  
	<p> 
	  Real-world data generation often involves complex inter-dependencies among instances, violating the IID-data hypothesis of standard learning paradigms and posing a challenge for uncovering the geometric structures for learning desired instance representations. To this end, we introduce an energy constrained diffusion model which encodes a batch of instances from a dataset into evolutionary states that progressively incorporate other instances’ information by their interactions. The diffusion process is constrained by descent criteria w.r.t. a principled energy function that characterizes the global consistency of instance representations over latent structures. We provide rigorous theory that implies closed-form optimal estimates for the pairwise diffusion strength among arbitrary instance pairs, which gives rise to a new class of neural encoders, dubbed as DIFFORMER, with two instantiations: a simple version with linear complexity for prohibitive instance numbers, and an advanced version for learning complex structures. Experiments highlight the wide applicability of our model as a general-purpose encoder backbone with superior performance in various tasks, such as semi-supervised node classification, image/text classification, and spatial-temporal dynamics prediction.
	</p> 
	

	Currently, no BibTex provided since it is anonymous

</details>


## DiffEdit
| | |
|--|--|
|Title|DiffEdit: Diffusion-based semantic image editing with mask guidance |
|Paper Link| https://arxiv.org/pdf/2210.11427.pdf |
|Institute | Meta AI|
| Github||

![Screenshot 2023-02-13 at 22 13 54](https://user-images.githubusercontent.com/115451386/218481453-be040bae-ae32-4771-a95f-6ee13cac6c2c.png)

1. **Task**
	semantic image editing, which is an extension of image generation
2. **Problem**
	Current editing methods usually provide a mask, and not treat it as a conditional inpanting task.
3. **Method**
	Automatically generate a mask by contrasting predictions of model conditioned on different text prompts.
4. **Performance**
	edit images in ∼10 seconds on a single Quadro GP100 GPU
5. **Dataset**
	ImageNet, images generated by Imagen, COCO
6. **Model's information**
	diffusion model: Stable Diffusion 512*512; 50 steps DDIM sampling; mask is 32^2 for ImageNet, 64^2 for Imagen and COCO.
	
<details>  
	<summary>Abstract and Bibtex</summary>  
	<p> 
Image generation has recently seen tremendous advances, with diffusion models allowing to synthesize convincing images for a large variety of text prompts. In this article, we propose DiffEdit, a method to take advantage of text-conditioned diffusion models for the task of semantic image editing, where the goal is to edit an image based on a text query. Semantic image editing is an extension of image generation, with the additional constraint that the generated image should be as similar as possible to a given input image. Current editing methods based on diffusion models usually require to provide a mask, making the task much easier by treating it as a conditional inpainting task. In contrast, our main contribution is able to automatically generate a mask highlighting regions of the input image that need to be edited, by contrasting predictions of a diffusion model conditioned on different text prompts. Moreover, we rely on latent inference to preserve content in those regions of interest and show excellent synergies with mask-based diffusion. DiffEdit achieves state-of-the-art editing performance on ImageNet. In addition, we evaluate semantic image editing in more challenging settings, using images from the COCO dataset as well as text-based generated images.
	</p> 
@article{couairon2022diffedit,
  title={Diffedit: Diffusion-based semantic image editing with mask guidance},
  author={Couairon, Guillaume and Verbeek, Jakob and Schwenk, Holger and Cord, Matthieu},
  journal={arXiv preprint arXiv:2210.11427},
  year={2022}
}
</details>



## Template
| | |
|--|--|
|Title| |
|Paper Link| |
|Institute ||
| Github||

1. **Task**
	
2. **Problem**
	
3. **Method**
	
4. **Performance**
	
5. **Dataset**
	
6. **Model's information**
	

<details>  
	<summary>Abstract and Bibtex</summary>  
	<p>   
	</p> 

</details>



