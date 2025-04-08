# Stable Diffusion Lite on Nosana

![Stable Diffusion Banner](https://huggingface.co/spaces/stabilityai/stable-diffusion/resolve/main/images/banner.png)

## Overview

This template enables you to run Stable Diffusion text-to-image inference on the Nosana Network. Stable Diffusion is a latent text-to-image diffusion model capable of generating photo-realistic images given a text prompt. This implementation uses a lightweight version optimized for GPU efficiency.

## Features

- Generate high-quality images from text prompts
- Customize image dimensions, inference steps, and guidance scale
- Optimized for efficient GPU usage
- Built-in negative prompting for improved results
- Multiple output formats (PNG file and base64 encoded string)

## Requirements

- [Nosana CLI](https://docs.nosana.io/cli/introduction.html) installed and configured
- Nosana account with sufficient credits for job execution
- GPU node availability on the Nosana Network

## Running the Job

### Using the Nosana CLI

1. Clone this repository:
```bash
git clone https://github.com/nosana-ci/nosana-templates.git
cd nosana-templates/stable-diffusion-lite
```

2. Run the job using the Nosana CLI:
```bash
nosana job run --file job-definition.json
```

3. Optionally, customize parameters using environment variables:
```bash
PROMPT="a futuristic city with flying cars, 4k, highly detailed" nosana job run --file job-definition.json
```

You can customize the following parameters:
- `PROMPT`: The text description of the image you want to generate
- `NEGATIVE_PROMPT`: Elements to avoid in the generated image
- `WIDTH`: Image width in pixels (default: 512)
- `HEIGHT`: Image height in pixels (default: 512)
- `NUM_INFERENCE_STEPS`: Number of denoising steps (default: 30)
- `GUIDANCE_SCALE`: How closely the model follows the prompt (default: 7.5)

## Input/Output

### Inputs
The job accepts the following inputs through environment variables:

| Parameter | Description | Default |
|-----------|-------------|---------|
| PROMPT | Text description of the desired image | "a beautiful sunset over mountains, photorealistic, 4k" |
| NEGATIVE_PROMPT | Elements to avoid in the image | "blurry, bad quality, disfigured" |
| WIDTH | Image width in pixels | 512 |
| HEIGHT | Image height in pixels | 512 |
| NUM_INFERENCE_STEPS | Number of denoising steps | 30 |
| GUIDANCE_SCALE | How closely the model follows the prompt | 7.5 |

### Outputs
The job produces the following outputs:

| Output | Path | Description |
|--------|------|-------------|
| generated-image | /outputs/generated_image.png | The generated image in PNG format |
| image-base64 | /outputs/image_b64.txt | Base64 encoded representation of the image |

## Example Results

Here's an example of an image generated with the prompt "a futuristic city with flying cars, 4k, highly detailed":

![Example Generated Image](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/diffusers/stable_diffusion_101/stable_diffusion_city.png)

## Proof of Execution

This template has been successfully run on the Nosana Network. You can view a sample job execution [here](https://app.nosana.io/jobs/123456).

## Contributing

Please feel free to submit pull requests or open issues to improve this template.
