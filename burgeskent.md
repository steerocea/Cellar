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

### Zombie Enemy [Level Of Input: All]:

I worked on the enemy of the dungeon, the zombie. Originally there were meant to be three enemies, but this went down to two and then one when the procedural generation was taking me longer and longer. My contribution to the zombie included finding its model and animations online, retargeting the animations to fit the rig I was using (The animations had more bones), blending the animations togther, writing the behavour tree for the zombies AI, writing the code for how it does actions, and finally adding the sound effects. I was planning to use thw knowledge I gained from creating the zombie to make the other enemies, but as I mentioned I didn't end up having enough time for this. 


### Procedural Generation [Level Of Input: All]:

Since I had a little more Unreal Engine experience than my teammates before this project, and I wants interested in the topic, I wanted to take on the writing of the procedural generation code, which was by far the largest part of the game I worked on. I started working on it before the prototype hand in, as I wanted to get ahead as I knew it could take me a while to get it right.

The procedural dungeon itself consists of a system of connecters, hallways and rooms. A number of iterations is set in the code, for example 20, which describes how large the dungeon will generate. At first a hallway is generated, and at its end a connecter. A connecter has three sides, left, forward and right, which it randomly decides whether to generate more hallways, a room, or just place a wall. When it generates a hallway or a room, it randomly picks from the multiple types of each one, to keep the dungeon interesting. There is also a system in place to remove hallways or rooms if they overlap anything else. If the dungeon reaches its max iterations, and there are at least five rooms in the dungeon, it is considered successful. 

However, if it stops before it reaches its max iterations (Enough overlap causes a connecter to not generate any hallways) it runs back through the dungeon, and any connecter sides that dont have hallways, it will try to generate more dungeon from. Another scenario is it reaches max iterations and didn't generate enough rooms, in which it will find any connecters with no hallways, and generate a room from those. All of this leads to a system which has a very high chance to generate a dungeon, and even if it fails, the level will reload and it will try again. 



### Dungeon Design and Layout [Level Of Input: All]:

Going alongside the dungeon generation, I was also tasked with making the dungeon rooms themselves, including the connecter, hallways and rooms. To do this I found some assets online, loaded them into blender, and then converted them to .fbx to edit or just load straight into Unreal. From there I created the hallways and rooms in Unreal itself, as I was more confidient in its editing system than blenders. Then I combined all the assets into one static mesh for fps, converted them to an actor so I could add code, and then manually added in the lighting, chests and enemy placement from inside the actors viewport. In the end I created the connecter, four hallway types and seven room types, six for random generation and one for the starting room. 


## Code Discussion Video:

[Link To Video]

## Most Interesting Blueprint I Wrote / The Blueprints I Am Most Proud Of::

While it had it flaws (Mentioned in worst blueprint code), I was very proud of my procedural system, for it being the first of its kind I had made. The main implementation of the system was split into four functions, two for during the generation and two for after. 

* Check If Stopped Early And Fix [During Generation]: This function existed to fix any problems that came with the generation, if the dungeon stopped genearing new hallways but wasn't at max iterations. It would pick a random ungenerated connecter side and generate more dungeon from it.

* Generate Dungeon [During Generation]: The main generation function, created connecters, and then depending on which side it chose, created more hallways or rooms from there. Deleted any hallways or rooms that overlapped eachother, and didn't count that towards the continued generation, so it could be continued elsewhere. 

* Spawn Rooms On All Empty Connecters [Post Generation]: After the generation of the dungeon, runs through all connecters again, using the trigger boxes surrounding them to find ones that didn't have any hallways generated from them. If so, generated a room to contibute to filling the dungeons success criteria.

* Is Done? [Post Generation]: Checks multiple factors for if the dungeon is finished generating, including if max iterations had been reached and if there are enough rooms. From there either generates the dungeon again for a maximum of 35 times until it is successful (This was the limit for looping the generation), if its still not successful just resets the level which runs the generation again, or hopefully it successfully generates, and spawnas the player into the dungeon.

![Procedural Functions](burgeskent-screenshots/proc-functions.PNG)

Another thing I was happy with was the system for adding in the hallway and room meshes. It was created in a way where it is very easy to add more, as you just needed the mesh itself and a macro (Small section of math) to calculate where to spawn it in relation to the where it is requested. An example of this is that the 0,0,0 for the staircase is in the middle of it, so for a connecter to spawn it, the macro has to include moving the staircase forward and up, to fit correctly. 

![Room Extendability](burgeskent-screenshots/proc-room-extendability.PNG)

## My Worst Blueprint Code:

![Spawn Connecters On Ends](burgeskent-screenshots/bad-proc-spawn-connecters-on-ends.PNG)

![Spawn Connecters On Ends](burgeskent-screenshots/bad-proc-connecter-collision-for-hallway-detection.PNG)

![Spawn Connecters On Ends](burgeskent-screenshots/bad-proc-connecter-collision-view.PNG)



## My Use Of ChatGPT:

Because of my use of primarily blueprints, AI like ChatGPT was slightly less useful. It would still be able to answer questions, but it would have a hard time describing how to solve blueprint based questions. However for overall Unreal questions, like certain settings or methods excluding blueprints, it still helped every now and then. This problem will be solved when I switch to C++ in the future, and I will be able to use other built in AI for help while coding as well.

# Learning Reflection:
## What I Learnt From This Project:

* Plan and make systems better from the start: Since it was my first time making a procedural system, I winged it from the start and didn't plan out much of the system. This meant that, for example, no generated paths can connect to other generated paths, because they don't line up correctly. However if I had planned the system to be grid based, I could have used something like the A-Star algorithm, to create paths between connecters, leading to a more accurate and detailed dungeon system. While I'm happy with the system I created, when realising this possibility half way through making it, it was already too late unless I rewrote the whole system.

* Don't rely entirely on blueprints: I have only worked in blueprints for all of my projects so far. And in making this procedural system, for the first time I felt as if making it in C++ would have been easier and more effective. I could have made things tider, used local variables more, implement systems that I don't know how to do in blueprints, and not have to deal with the messy layout of the blueprints system. On top of that, C++ code even runs better than blueprints, which would have helped dramatically with the generation time for the dungeon. 

* Use Blender for large asset creation: Making the dungeon rooms took a long time. This is because if I ever needed to change any part of the layout, I would need to go back into the unreal creation world, ungroup the orignial assets, make the change, regroup them, move them to 0,0,0 and then recombine them into one static mesh, hoping they were centered enough for the axis to work with my system. I worked with the unreal system because I was more confident in it than blender, but I now realise that using blender would have streamlined much of this process, enabling much easier movement of the axis, and combining into one mesh. 

## Most Important Thing I Will Use In Future Projects:

* Using C++: After what I mentioned in the section above, it is clear to me that I should make an entire project in C++ to learn the ropes and really see the benefits it provides. This will also give me a much better understanding of the Unreal Engine itself, as some systems work slightly differently with C++ than they do with blueprints. 

* Outsourcing work: While our smaller group size didn't allow for this, if we had a larger group I would have liked to oursource the dungeon room creation to another team member, and work with them to make the dungeon. This is because making the dungeon rooms took a large chunk of my time that could have gone towards furthering the development of the procedural system, fixing bugs, and polishing.
