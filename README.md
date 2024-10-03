
# Project Overview

This project involves creating a short 2-minute video using GenAI tools for script, image, voice, and music generation. The project integrates various AI-based technologies to create a seamless workflow from script generation to final video production.

## Procedure

1. **Generate Script**: Use GenAI text-to-text tools to create a script. See [Detail Steps for Generate Script](#detail-steps-for-generate-script) for more information.
2. **Parse and Build Context for Scene Generation**:
   - Extract the **positive** and **negative** prompts for each scene.
   - Use GenAI text-to-image (text2img), image-to-image (img2img), or a hybrid method to generate visuals either manually or programmatically.
3. **Prepare Voiceover**: Use a text-to-voice tool to convert the script's voiceover into audio files.
4. **Prepare Music**: Use GenAI text-to-music tools, either manually or by generating music based on scene descriptions.
5. **Compile the Video**: Combine the scenes, voiceover, and music into one cohesive video using a simple video editor.

## Detail Steps for Generate Script

To generate the script, use the following template to create the scenes, visuals, and voiceover scripts. This ensures each part of the scene (e.g., positive and negative prompts) is ready for image generation and can be assembled into a short scene.
```markdown
### Script Request Example:
> "Give me a script of the history of [insert user preference, e.g., dance] for a 2-minute video. It contains scenes, visuals, and a voiceover script. For the visuals, embed well-known artists or characters with a funny/comedy vibe. Breakdown the visuals into multiple image generation prompts for an LLM which at the end can be compiled into a short scene. Provide both positive and negative prompts."
Follow this json format:

```json
{
  "Title": "<insert movie title>",
  "Scene <number>": "<insert scene title>",
  {
    "Description": "<description of the scene>",
    "Voice over": "<insert the voiceover script>",
    "Visual": {
      "<time in seconds>": {
        "positive": "<insert positive prompt to generate image>",
        "negative": "<insert negative prompt to make sure the quality and consistency>"
      },
      "<another time in seconds>": {
        "positive": "<insert positive prompt to generate image>",
        "negative": "<insert negative prompt to ensure quality and consistency>"
      },
      "<another time in seconds>": {
        "positive": "<insert positive prompt to generate image>",
        "negative": "<insert negative prompt to ensure quality and consistency>"
      }
    }
  }
}
```

### Example Script for Dance Video:

```json
{
  "Title": "The Hilarious History of Dance",
  "Scene 1": "The Dawn of Dance",
  {
    "Description": "A caveman, clumsy but excited, discovers dancing for the first time. Famous prehistoric character Fred Flintstone joins in the fun, bringing laughter to the prehistoric era.",
    "Voice over": "In the beginning, dance wasn't graceful—it was... a bit of a stumble.",
    "Visual": {
      "1s": {
        "positive": "A prehistoric caveman clumsily dancing with Fred Flintstone in a rocky terrain. Both are making goofy faces. The dance looks more like jumping and stumbling. Primitive, stone-age background.",
        "negative": "Avoid modern clothing, smooth choreography, or advanced environments."
      },
      "4s": {
        "positive": "Caveman trips over a rock mid-dance, but spins to recover, Fred Flintstone laughing heartily in the background. The movement looks accidental and funny.",
        "negative": "No realistic falling or injuries, avoid serious expressions or realistic stone textures."
      }
    }
  }
}
```

## Tools and Technologies Used

- **GenAI text2text**: For generating the script and scene breakdowns.
- **GenAI text2img / img2img**: For generating images based on positive and negative prompts.
- **Text-to-voice tools**: For converting the voiceover script into audio.
- **GenAI text2music**: For creating music based on scene descriptions or manually creating music for the video.
- **Simple Video Editor**: For compiling all the elements (images, voiceover, music) into the final video.

## Notes

- Ensure all AI-generated content aligns with your project’s tone and style.
- Fine-tune image generation prompts to ensure the visual consistency across scenes.
```

