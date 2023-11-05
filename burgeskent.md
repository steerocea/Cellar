 # Info
 * Name: Kent Burgess
 * Username: burgeskent
 * Project Role: Enemies, Map Design, Procedural Generation
 * Animal Role: Wolf

# Group Contribution:
## My Contribution To The Group / My Communication Role:

For this project I had the Wolf role, so my job was being the manager and keeping the group together. Since we didn't have a Bear in the group (An overall leader), for the most part that job was given to me. I think I did pretty well for my first time leading a group, I would keep up to date on my teammates work and provide ideas or motivation if needed. This included setting meeting times, and talking to each teammate individually about their progress. 

## Group Dynamics:

I think we worked decently well as a team, as we all would ask for help if needed and provide it as well. The discord helped greatly in our fast communication, and most of the time we were all online to assess any problems with the project. One of the only things I think we could improve on is time management, as in the first half of the project due to other uni work, both my teammates didn't work on the project until shortly before the prototype hand in.
Another problem that isn't our teams fault is just the lack of team members we had. Most teams had 5-6 people, but we had 3. This meant we had to scale down our project in either the size or quality to compensate for this, which I think we did effectively. One of the benefits however of a smaller team was easier communication, and less chance for GitLab pushing / pulling issues because of many people working in different areas. 

# Code Discussion:
## Parts Of The Project I Worked On:

Zombie Enemy [Level Of Input: All]:

I worked on the enemy of the dungeon, the zombie. Originally there were meant to be three enemies, but this went down to two and then one when the procedural generation was taking me longer and longer. My contribution to the zombie included finding its model and animations online, retargeting the animations to fit the rig I was using (The animations had more bones), blending the animations togther, writing the behavour tree for the zombies AI, writing the code for how it does actions, and finally adding the sound effects. I was planning to use thw knowledge I gained from creating the zombie to make the other enemies, but as I mentioned I didn't end up having enough time for this. 


Procedural Generation [Level Of Input: All]:

Since I had a little more Unreal Engine experience than my teammates before this project, and I wants interested in the topic, I wanted to take on the writing of the procedural generation code, which was by far the largest part of the game I worked on. I started working on it before the prototype hand in, as I wanted to get ahead as I knew it could take me a while to get it right.

The procedural dungeon itself consists of a system of connecters, hallways and rooms. A number of iterations is set in the code, for example 20, which describes how large the dungeon will generate. At first a hallway is generated, and at its end a connecter. A connecter has three sides, left, forward and right, which it randomly decides whether to generate more hallways, a room, or just place a wall. When it generates a hallway or a room, it randomly picks from the multiple types of each one, to keep the dungeon interesting. There is also a system in place to remove hallways or rooms if they overlap anything else. If the dungeon reaches its max iterations, and there are at least five rooms in the dungeon, it is considered successful. 

However, if it stops before it reaches its max iterations (Enough overlap causes a connecter to not generate any hallways) it runs back through the dungeon, and any connecter sides that dont have hallways, it will try to generate more dungeon from. Another scenario is it reaches max iterations and didn't generate enough rooms, in which it will find any connecters with no hallways, and generate a room from those. All of this leads to a system which has a very high chance to generate a dungeon, and even if it fails, the level will reload and it will try again. 

The system for adding in the hallway and room meshes was created in a way where it is very easy to add more, as you just needed the mesh itself and a macro (Small section of math) to calculate where to spawn it in relation to the where it is requested. An example of this is that the 0,0,0 for the staircase is in the middle of it, so for a connecter to spawn it, the macro has to include moving the staircase forward and up, to fit correctly. 


Dungeon Design and Layout [Level Of Input: All]:

Going alongside the dungeon generation, I was also tasked with making the dungeon rooms themselves, including the connecter, hallways and rooms. To do this I found some assets online, loaded them into blender, and then converted them to .fbx to edit or just load straight into Unreal. From there I created the hallways and rooms in Unreal itself, as I was more confidient in its editing system than blenders. Then I combined all the assets into one static mesh for fps, converted them to an actor so I could add code, and then manually added in the lighting, chests and enemy placement from inside the actors viewport. In the end I created the connecter, four hallway types and seven room types, six for random generation and one for the starting room. 


## Code Discussion Video:

## Most Interesting Blueprint I Wrote:

## The Blueprints I Am Most Proud Of:

## My Worst Blueprint Code:

## My Use Of ChatGPT:

# Learning Reflection:
## What I Learnt From This Project:

## Most Important Thing I Wil Use In Future Projects:
