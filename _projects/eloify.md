---
layout: post
title: eloify
description: use the ELO rating system to streamline studying.
thumbnail: /assets/images/thumbnails/stippledalok.png
---



The Project
============


I really love chess puzzles. Like magic, websites like lichess or chess-tempo managed to extract interesting positions, use crowdsourcing to find which ones were actually tactically challenging, and serve users puzzles which match their skill levels. 

The way this system works is through ELO. ELO is a system generally used in PvP style games, where each user is assigned a prediction of their skill that goes up or down relative to their wins and losses. If you beat a better opponent, your predicted skill goes up by a larger quantity than a weaker opponent. 

Chess puzzles are a slight tweak to this system. It treats both puzzles and users as a part of the *same pool*, but as users that can never go up against one another. In this way, both puzzles and users can be evaluated relative to their peers, allowing users to get matched with tactics targeted towards their rating. 

Eloify generalizes this process. What if instead of being restricted to chess puzzles, you could drop in your course textbook or exams and turn that into a meaningful question bank to be queried? 


Implementation
------------
### Architecture ###
I used React, Django, and PostgreSQL as the foundational frameworks of the project. For frontend, I used the tried-and-tested React Bootstrap pretty extensively for beautiful, prebuilt components with minimal boilerplate and setup required. 

### Documents ###

After experimenting with some OCR and document querying models, I found these to ultimately be ineffective. There exists no centralized dataset for question and answer segmentation for document layout, and fine-tuning existing models would likely be a labourious process requiring copious amounts of training data. 

I instead decided to use a functional extension of the VQA built into multimodal LLMs. In my case, I feed these into a gemini flask model, then query the model for structured JSON of all questions provided on the page. Later, I can either scrape corresponding solutions or generate solutions and test cases on the fly. On the site, users can drag-and-drop questions into the applications and place them into study sets, which can be accessed by all users. 


### Code ###

Another interesting challenge was code — how can you create an environment in which users can run Python snippets for validation of Python exams, while having it be correctly sanitized? The solution lied in Docker. This was my first time using Docker, period! My solution involved creating a new container for each user, with limited scope and resources, and allowing them to run their code in that traiged environment, free from any injection attacks. Setting this up was definitely pretty cool, and is a tool I'm definitely keeping in my toolbox for future websites. 

Most other features served to be pretty standard problems, including users, question storage and retrieval, and LLM oriented question tagging. 

The site is still somewhat of a WIP, so I haven't gotten around to pushing it out for production use, but here's the Github: https://github.com/alokthakrar/elockedin