# AI Workflow Canvases Can Now Generate 3D Worlds. Here's What That Means.

Google DeepMind just launched Project Genie, built on Genie 3, generating fully interactive 3D worlds from a text or image prompt at 20 to 24 frames per second. You can walk through them in real time. The AI generates the path ahead as you move. It's the most impressive demonstration of AI world generation we've seen.

But Genie is a research prototype. It's available through Google Labs for AI Ultra subscribers in the US. You can explore short interactive environments, but you can't connect it to your creative workflow. You can't feed the output into a video pipeline. You can't import 3D objects, compose a scene, and capture production-ready renders.

Meanwhile, in the node-based AI canvas space, every tool generates flat images. Every workflow produces 2D outputs. You can upscale them. You can animate them into video. But you cannot walk through them.

[Raelume](https://raelume.ai) just shipped something that bridges this gap. Their Worlds blocks take any 2D image and convert it into a 3D Gaussian splatting environment. You can add objects to the scene. You can move a camera freely through the space. You can capture 1K, 2K, or 4K images from any angle. And soon, you'll be able to view these environments in VR.

![Worlds blocks on Raelume's node-based canvas](https://pbl.raelume.ai/docs/852_1x_shots_so.jpeg)

To be clear: this is not Genie. Worlds environments are explorative, not interactive. You move a camera through a reconstructed 3D space, not a dynamically generated game world. But it's the first time any node-based AI creative canvas has brought 3D world generation into the workflow at all. And unlike Genie, the output plugs directly into a production pipeline with 70+ AI models.

## From Genie to Gaussian Splatting: Two Approaches to AI Worlds

Google's Genie 3 and Raelume's Worlds represent two fundamentally different approaches to AI-generated 3D environments.

**Genie 3** is a world model. It generates the environment dynamically as you interact with it, predicting what comes next based on your actions. Think of it as an AI that builds the world around you in real time. It's interactive, running at 20 to 24 fps, and the results are stunning. But it's a research prototype available only through Google Labs, and its outputs don't connect to any creative production workflow.

**Gaussian splatting** takes a different path. It reconstructs 3D scenes from 2D images using millions of small, overlapping ellipsoids (the "splats"), each with a position, color, opacity, and shape. When rendered from a given viewpoint, these splats blend together to produce photorealistic imagery. The technique emerged from academic research in 2023, and the key advantage over older methods like NeRF (Neural Radiance Fields) is speed: Gaussian splatting renders in real time on consumer hardware.

Standalone Gaussian splatting tools already exist. You can find apps and command-line utilities that do the conversion. What's new is having it integrated into a node-based AI creative canvas where the output feeds directly into your next step. That's what Raelume built with Worlds.

## The Before and After

Here's what producing a 3D scene from an AI-generated image looked like before Worlds:

1. Generate your base image in Midjourney, DALL-E, or another image generator
2. Export the image
3. Open Blender (or similar 3D software)
4. Learn Blender if you don't already know it
5. Set up the scene, lighting, and camera
6. Manually position objects
7. Render
8. Export back to your workflow

This process assumes you have 3D skills. Most creative professionals working with AI tools don't. The gap between "I generated a cool image" and "I have a 3D environment I can explore" was measured in hours of work and months of learning.

With Worlds, the workflow becomes:

1. Generate image
2. Connect to Worlds block
3. Move camera, add objects
4. Capture
5. Done

The difference isn't just convenience. It's accessibility. Creative teams who previously outsourced 3D work or skipped it entirely can now incorporate spatial content into their pipelines without hiring specialists or learning new software.

## How Worlds Blocks Work in Practice

The mechanics are straightforward, which is the point.

**Step 1: Image Input**
Start with any 2D image. This could be something you generated in Raelume using one of their 70+ AI models (Flux 2 Pro Ultra, Nano Banana Pro, Kling 3 Pro, and others), or an image you've imported from elsewhere. The source doesn't matter.

**Step 2: Gaussian Splatting Conversion**
Connect the image to a Worlds block. Optionally connect a Prompt Agent or Prompt block for scene direction and style guidance. The system converts the flat image into a 3D Gaussian splatting environment. This isn't a simple depth map. The algorithm infers spatial relationships, reconstructs occluded areas where possible, and produces a navigable 3D space.

**Step 3: Scene Composition with 3D Object Import**
Once inside the environment, connect 3D blocks and place imported objects anywhere in your world. Each object gets full position, rotation, and scale controls. This turns static environments into populated, art-directed spaces.

**Step 4: Multi-World Composition**
Here's where it gets interesting. You can connect multiple Worlds blocks together to combine separate worlds into one immersive scene. Generate a forest, generate a castle, merge them. Each world becomes a building block for something larger.

**Step 5: Camera Movement and Capture**
Open the world in fullscreen mode. Move through it freely. Frame your shot. Capture at 1K, 2K, or 4K resolution. Each capture is created as a new Image node on the canvas, immediately available for downstream workflows. Feed it into a video block, upscale it, run it through another Worlds block. The output loops back into the pipeline.

![Worlds block interface showing 3D environment controls](https://pbl.raelume.ai/docs/319_1x_shots_so.jpeg)

The entire process happens on the canvas. No exports. No external software. No context switching.

**Pro tip from testing:** Start from clean source images with clear depth cues and strong lighting. Keep text prompts focused on mood, environment, and composition. Connect your 3D and Worlds blocks before entering build mode so assets are ready to place. And capture multiple angles to quickly branch into downstream image workflows.

## Use Cases That Weren't Possible Before

**Concept Art Exploration**
Concept artists typically produce single hero images. With Worlds, a single generated environment becomes a source of multiple shots. Generate the establishing scene once, then capture the wide shot, the closeup, the low angle, the aerial view. A single generation multiplies into a complete visual package.

**Product Visualization**
E-commerce teams need product shots from multiple angles. The traditional approach: photograph once, reshoot if you need a different angle. With Worlds, generate a product render, place it in a 3D scene, and capture as many angles as the campaign requires. No reshoots.

**Marketing Asset Production**
Campaign teams often need the same scene from different perspectives for different formats. Hero image for the landing page. Cropped version for social. Detail shot for the email header. One Worlds environment, multiple outputs.

**VR Content Previsualization**
With VR viewing coming soon, Worlds becomes a bridge between 2D AI generation and spatial computing. Generate a scene, explore it in VR, capture stills for the flat-screen version. One source, multiple destination formats.

## Where Other Node-Based Canvases Stand on 3D

I looked at every major node-based AI canvas to see who else is doing 3D.

**Krea:** Impressive real-time generation, 50+ models. No 3D or Gaussian splatting.

**Fuser:** 200+ models in a node-based workflow. No 3D capabilities.

**Freepik Spaces:** 36+ image models, 9+ video models, strong editing suite. No 3D.

**Flora:** Design-focused canvas. No 3D.

**ComfyUI:** The closest alternative. The open-source community has built Gaussian splatting extensions (ComfyUI-3D-Pack, ComfyUI-Sharp). They work. But ComfyUI is a developer tool. You're installing custom nodes from GitHub, managing Python dependencies, and debugging pipelines. There's no fullscreen world explorer, no multi-world composition, no drag-and-drop 3D object placement. It's powerful if you're technical. It's not accessible if you're a creative professional who wants to generate a world and start capturing shots.

That's the gap Worlds fills. Not "nobody else can do Gaussian splatting" (they can), but nobody else has made it a native, integrated part of a creative workflow canvas that non-technical users can actually pick up and use.

## Why 3D Is the Next Frontier for AI Creative Tools

The trajectory of AI creative tools has followed a predictable path: text first, then images, then video, then audio. Each step increased the dimensionality and complexity of the output. But all of these outputs share a common constraint: they're flat.

3D is the logical next step. Google knows it (Genie 3). Apple knows it (Vision Pro). Meta knows it (Quest). Spatial computing is arriving, and the creative tools need to catch up.

The question was never whether AI tools would move into 3D generation. The question was which tool would integrate it into creative workflows first, in a way that's actually usable for production work.

Genie 3 is the most impressive pure demonstration. But it's a research prototype, not a creative tool. Raelume made a different bet: 3D shouldn't be a separate application or a research demo. It should be a block, like any other block, that connects to the rest of your workflow. Image in, 3D environment out, captures back into the pipeline.

This is a design philosophy as much as a feature. The AI creative tool space has suffered from fragmentation: one subscription for images, another for video, another for audio, yet another for 3D. Raelume's model ("One subscription. Every model.") pushes in the opposite direction. 70+ models. Six media types: Image, Video, 3D, Audio, Text, and Worlds. All on one canvas.

## Why This Matters for Creative Teams

The practical impact breaks down into a few categories:

**Reduced software stack.** Teams currently juggling multiple subscriptions and export/import workflows between applications can consolidate. The 3D capability that previously required Blender expertise now lives in the same canvas as image generation.

**Faster iteration.** When the 3D step is on the same canvas as everything else, you remove the friction that slows down creative iteration. Try something, see if it works, move on. No file management. No application switching.

**Accessible 3D.** Gaussian splatting is not a simple technique. The math is dense. The implementation is non-trivial. By abstracting all of that behind a block interface, Raelume makes spatial content accessible to teams who don't have 3D specialists on staff.

**New output formats.** With VR viewing on the roadmap, Worlds blocks become an on-ramp to spatial content. Teams can start producing VR-compatible environments today, before they've invested in VR-specific workflows.

## The Current State and What's Coming

Worlds is live today with image-to-Gaussian-splatting conversion, 3D object placement, free camera movement, and 2K to 4K capture.

VR viewing is listed as "coming soon." This will allow users to step into their Worlds environments using a headset, moving from a desktop preview to full immersion.

I'll be watching to see how the feature evolves. The core technology is solid. The integration into the node-based workflow is well-executed. What happens next depends on how the creative community uses it and what new capabilities get added.

## The Bottom Line

The AI creative tool space has been racing to add more models, more output formats, more features. In that race, everyone focused on 2D. More image models. Better video quality. Higher resolution.

Raelume took a different turn. They asked what happens when you let the user step inside the image. The answer is Worlds: Gaussian splatting environments that you can explore, compose, and capture from any angle.

For creative teams working on anything spatial, this is the capability that changes the tooling equation. And for everyone else, it's a preview of where the entire category is heading.

3D is no longer separate from the AI workflow. It's a block, connected like any other.