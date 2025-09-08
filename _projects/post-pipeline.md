---
layout: post
title: Brainrot Generator
description: Uses open source TTS models, MoviePy, and Reddit + YouTube APIs to automate reddit stories.  
thumbnail: /assets/images/projects/brainrot.png
---

Brainrot Pipeline
============
I'm unfortunately a victim to the IG reels epidemic, reddit stories included. But after I got a few on my feed, I realized that this would be relatively simple to automate, and go even further. 


Brainrot Pipeline
-----------
The pipeline is relatively intuitive. Posts are scraped from user-provided subreddits (e.g. Malicious Compliance) and shorter ones are selected. The bot then passes this into Kokoro https://huggingface.co/hexgrad/Kokoro-82M, an open source TTS model which can be run locally, which provides the voiceover. The voiceover is pasted over a video of Minecraft parkour or Subway Surfers, subtitles are generated through MoviePy, and the post gets uploaded to Youtube Shorts automatically.

WIP (The next step)
-----------
The reason why I ultimately set up this pipeline was actually for a slightly different purpose — a generalized paper scraper. It'd go through the most recent hot papers in CS, bio, physics, etc, generate a silly summary using a Peter Griffin voice with an LLM, and paste that under the same parkour and subtitle style videos. This, however, requires data to fine-tune the voice model to sound like a fictional character (e.g. Peter Griffin) I'm currently working on a method of using open-source subtitles to automatically clip out relevant character voices, and to feed that into a data-bank of weights for public use. Will update once/if complete, but the end result should hopefully be pretty cool!