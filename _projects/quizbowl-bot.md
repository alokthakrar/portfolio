---
layout: post
title: QuizBot
description: First functional voice-based quizbowl system. Same format as official online tournaments, power points included.
redirect: 
thumbnail: /assets/images/projects/QuizBot.png
---


QuizBot
============
I was bitten by the Quizbowl bug my freshman year of high school. Back during COVID, the main method which our tournaments were carried out was through discord, with a moderator reading out the questions to participants, and I wanted a system to familiarize myself with that style of Q&A. 


The Project
-----------
This was back in the era where TTS was a difficult, laborious process. I first aggregated questions from a public question bank, then fed them into Google's TTS API. 

The most challenging part of this was integrating the bot with Discord. The Discord API didn't directly support bots playing audio programatically, so it took some workarounds inspired by music bots of the time to get that to work. Powers, or bonus points before a marker, were computed by cross referencing the amount of audio played to the time stamp of where the power was supposed to be in the spoken audio before a preprocessed removal from the TTS call. 

Things like points and buzzes were directly managed through the chat, and all taken care of by the bot script. Unfortunately our QuizBowl club got shut down the very next year, but this bot did get me my first high school yearbook feature #oneofthecoolkidsnow

