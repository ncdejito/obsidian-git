[[Deep Learning]]

Stable Diffusion

https://github.com/lllyasviel/ControlNet
StableDiffusion WebUI [colab notebooks](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Online-Services#google-colab)

Commercial APIs
OpenAI’s DallE2 2c/image pricing
Create image
```
response = openai.Image.create(
  prompt="a white siamese cat",
  n=1,
  size="1024x1024"
)
image_url = response['data'][0]['url']
```
Huggingface’s Stable Diffusion 0.2c/image pricing
Create image
```
from diffusers import StableDiffusionPipeline
import torch

torch.manual_seed(42)

pipe = StableDiffusionPipeline.from_pretrained("CompVis/stable-diffusion-v1-4", revision="fp16", torch_dtype=torch.float16).to("cuda")

base_prompt = "portrait of a woman, head and shoulders, wearing a coat, high quality, photograph"
base_seed = 22291359391605

image = pipe(
    base_prompt,
    generator = torch.Generator(device='cuda').manual_seed(base_seed),
    num_inference_steps=40).images[0]
```
Craiyon - unli images 20s wait per image 20$/mo pricing, unofficial API
```
from craiyon import Craiyon

generator = Craiyon() # Instantiates the api wrapper
result = generator.generate("Photorealistic image of shrek eating earth")
result.save_images() # Saves the generated images to 'current working directory/generated', you can also provide a custom path
```
Midjourney - unli images 1-2min wait per image 60$/mo pricing
API is Discord command
Need some way to listen for replies on Discord to create custom app
Discord Receiving and Responding
Muse - fastest but API unavailable, 10x faster than Imagen, 3x faster than Stable Diffusion
Google’s Imagen - slow, no programmable API

Save Image
```
# https://stackoverflow.com/a/8286397
import urllib
resource = urllib.urlopen("http://www.digimouth.com/news/media/2011/09/google-logo.jpg")
output = open("file01.jpg","wb")
output.write(resource.read())
output.close()
```

Demo
- Model websites
DALL-E2
Stable Diffusion dreamstudio
CraiyonAI (formerly DALLE-Mini)
MidJourney (on discord)
BrancherAI - no code

Prompt generation
-as specific as you can
Stable Diffusion prompt guide
Promptbuilder
AI Image prompt generator
Awesomeprompts github
Docs
DALL-E2 docs
Stable Diffusion quickstart

Papers
[2023Jan4] SOTA Survey GenerativeAI - catalog of cutting edge models, including text to video/music also
[6yrs ago] Paperswithcode Text-to-image - outdated repos
Where has it been trained? ImageNet embeddings?
What’s the compute required?
Custom data?
DALL-E2 - generation from images contrasted and natural language info
Stable Diffusion - latent diffusion, better quality
DALL-E Mini - no GPU needed, source

Concepts
Contrastive learning - enhances the performance of vision tasks by using the principle of contrasting samples against each other to learn attributes that are common between data classes and attributes that set apart a data class from another
Transformer models - differentially weighting the significance of each part of the input data, used in CV and NLP
Auto-encoders - type of artificial neural network used to learn efficient codings of unlabeled data
CLIP embeddings - Contrastive Language-Image Pre-Training, not directly optimizing for the benchmark, learning visual representations from natural language supervision, like a Gaussian Mixture Model
Latent variables - variables that can only be inferred indirectly through a mathematical model from other observable variables that can be directly observed or measured
U-nets - neural network with downsampling and upsampling of images using pooling layers, used in Semantic Segmentation, shaped like a U
Resnets - creating connections between layers to avoid vanishing gradients

Courses
Deep Learning Specialization by Andrew Ng yt playlist
[TBA] FastAI with Generative models - blogpost
Illustrated Stable Diffusion blogpost

Community
#generative - what’s being discussed
Astronaut horse club - just contains fastai link

Code
stablediffusion code by Adam Kelly
Stable Diffusion code samples
vq-diffusion
parti-pytorch
