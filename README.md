# cantina-galactic-gunners
Vibe Coded self contained HTML Shoot ’em up game. 

> Use at own risk. I have LITERALLY vibe-coded 95% of this. Have absolutely no idea what the code does but it works and it's fun. Start it up with VSCode Live Server to load assets.
> 
> Enjoy!

<img width="956" alt="Screenshot 2025-05-26 154349" src="https://github.com/user-attachments/assets/49f4462a-e753-4b68-84b5-5f432f6cc207" />


## Features

### Tracking
Hearts tracking number of lives, score and kills.

<img width="80" alt="Screenshot 2025-05-26 152931" src="https://github.com/user-attachments/assets/67997a87-202b-4a6c-aba0-28f59ae0a4d2" />

### Achievements
List of achievements that unlock after certain 'secret' conditions are accomplished.

<img width="298" alt="Screenshot 2025-05-26 152826" src="https://github.com/user-attachments/assets/e18e3de4-594e-46cf-b1e9-4b26e51993da" />

### Time Based Quests
Quests with timed goals: kill count, survive, collect weapons, reach score.. for bonus points.

<img width="196" alt="Screenshot 2025-05-26 153140" src="https://github.com/user-attachments/assets/ca2a1141-8feb-4bad-9288-cc7b8bbc38cf" />

### Power Ups and Weapon System
Standard laser fire plus special weapon modes:super double-damage, 360-spray, mega-ray beam.
Periodic power-ups: speed boost, extra life heart and shield.
God mod available for infinite lives. Find it yourself in the code.

<img width="581" alt="Screenshot 2025-05-26 153315" src="https://github.com/user-attachments/assets/9d28be2f-ace4-43a9-8c04-be67015788c7" />

### Boss Battle
Boss battle against Lazarus every 2 000 points: spiral projectiles, health bar, unique rewards 
*You need to add the face asset yourself, else its just a pink square.*

<img width="952" alt="Screenshot 2025-05-26 153647" src="https://github.com/user-attachments/assets/04daa4c5-ea3b-4885-b791-c36ae978d92d" />

### "Video Calls"
Periodic “video-call” banter from characters triggered by score milestones.

<img width="703" alt="Screenshot 2025-05-26 154244" src="https://github.com/user-attachments/assets/df215f3e-1180-45ac-a721-a72f63eee42f" />



## Technical Overview

- **Pure-JS HTML5 canvas renderer** – a single `<canvas>` element fills the window and all graphics are produced with the 2-D context; no external engine or framework is required.
- **`requestAnimationFrame` main loop** – drives physics, AI and drawing each frame, with a simple `state` flag for “playing” versus “gameOver.”  
- **Data-driven entities** – enemy stats and behaviours live in an `enemyTypes` object, while the boss has its own `bossType` record for the spiral attack pattern.   
- **Dynamic world system** – portals shift the scene between Normal, Cyber and Quantum realms; a `worldSystem` module repaints layered gradients and applies per-world speed modifiers. 
- **Input & weapons** – WASD / arrow keys and optional touch controls feed velocity-based movement; `shoot()` spawns varied lasers or a beam depending on the active power-up.   
- **Difficulty scaling & quests** – score-based functions ramp enemy speed, while timed quests and achievements are tracked via `questState` and `achievementState` objects.   
- **Asset pipeline** – SVG sprites for player, NPCs and enemies are pre-loaded with `new Image()` from the `/assets/` folder to avoid runtime fetch delays. 
- **Lightweight packaging** – audio stubs stand in for future sounds, and everything ships inside a single `game-checkpoint.html` file, so running any static HTTP server is enough to play.
