# AI Workflow Canvases Can Now Generate 3D Worlds

Google DeepMind launched Project Genie, built on Genie 3, generating fully interactive 3D worlds from a text or image prompt at 20 to 24 frames per second. You can walk through them in real time. The AI generates the path ahead as you move. It's the most impressive demonstration of AI world generation we've seen.

But Genie is a research prototype. It's available through Google Labs for AI Ultra subscribers in the US. You can explore short interactive environments, but you can't connect it to your creative workflow. You can't feed the output into a video pipeline. You can't import 3D objects, compose a scene, and capture production-ready renders.

Meanwhile, in the node-based AI canvas space, every tool generates flat images. Every workflow produces 2D outputs. You can upscale them. You can animate them into video. But you cannot walk through them.

[Raelume](https://raelume.ai) shipped WORLDS blocks that bridge this gap. They take any 2D image and convert it into a 3D Gaussian splatting environment. You can add objects to the scene, move a camera freely, and capture 1K, 2K, or 4K images from any angle.

## From Genie to Gaussian Splatting: Two Approaches

**Genie 3** is a world model. It generates the environment dynamically as you interact with it, predicting what comes next based on your actions. It's interactive, running at 20 to 24 fps. But it's a research prototype with outputs that don't connect to creative production workflows.

**Gaussian splatting** reconstructs 3D scenes from 2D images using millions of small, overlapping ellipsoids (the "splats"), each with a position, color, opacity, and shape. When rendered from a given viewpoint, these splats blend together to produce photorealistic imagery. The technique emerged from academic research in 2023, with the key advantage over NeRF being speed: Gaussian splatting renders in real time on consumer hardware.

## How WORLDS Blocks Work

**Step 1: Image Input**
Start with any 2D image. This could be generated with AI models (Flux 2 Pro Ultra, Nano Banana Pro, etc.) or imported from elsewhere.

**Step 2: Gaussian Splatting Conversion**
Connect the image to a WORLDS block. Optionally connect a Prompt block for scene direction and style guidance. The system converts the flat image into a 3D Gaussian splatting environment, inferring spatial relationships and reconstructing occluded areas.

**Step 3: 3D Object Import**
Place imported 3D objects anywhere in your world. Each object gets full position, rotation, and scale controls.

**Step 4: Multi-World Composition**
Connect multiple WORLDS blocks together to combine separate worlds into one scene. Generate a forest, generate a castle, merge them.

**Step 5: Camera Movement and Capture**
Open the world in fullscreen mode. Move through it freely. Frame your shot. Capture at 1K, 2K, or 4K resolution. Each capture becomes a new Image node on the canvas for downstream workflows.

## Use Cases

**Concept Art Exploration**
Generate the establishing scene once, then capture the wide shot, closeup, low angle, and aerial view. One generation, multiple outputs.

**Product Visualization**
Generate a product render, place it in a 3D scene, capture as many angles as the campaign requires. No reshoots.

**Marketing Asset Production**
One WORLDS environment produces hero images, social crops, and email headers from different perspectives.

**VR Content Previsualization**
With VR viewing coming soon, WORLDS becomes a bridge between 2D AI generation and spatial computing.

## Where Other Node-Based Canvases Stand

- **Krea:** Real-time generation, 50+ models. No 3D or Gaussian splatting.
- **Fuser:** 200+ models in node-based workflow. No 3D capabilities.
- **Freepik Spaces:** 36+ image models, 9+ video models. No 3D.
- **ComfyUI:** Open-source, has Gaussian splatting extensions. But it's a developer tool requiring Python dependencies and debugging. Not accessible for non-technical users.

## Why 3D Is the Next Frontier

AI creative tools have followed a trajectory: text, then images, then video, then audio. Each step increased dimensionality. But all outputs are flat.

3D is the logical next step. Google knows it (Genie 3). Apple knows it (Vision Pro). Meta knows it (Quest). Spatial computing is arriving.

The question was never whether AI tools would move into 3D. The question was which tool would integrate it into creative workflows first, in a way that's usable for production work.

WORLDS represents a design philosophy: 3D shouldn't be a separate application. It should be a block, like any other block, that connects to the rest of your workflow. Image in, 3D environment out, captures back into the pipeline.

## Best Practices

- Start from clean source images with clear depth cues and strong lighting
- Keep text prompts focused on mood, environment, and composition
- Connect 3D and WORLDS blocks before entering build mode so assets are ready
- Capture multiple angles to quickly branch into downstream workflows

## What's Coming

WORLDS is live with image-to-Gaussian-splatting conversion, 3D object placement, free camera movement, and 2K to 4K capture.

VR viewing is listed as "coming soon," allowing users to step into their WORLDS environments using a headset.

3D is no longer separate from the AI workflow. It's a block, connected like any other.
