# Prototype Group Reflection 

brief summary of group reflection (how we worked together maybe)

## Levi (Weapons):

Solo reflection on your part of the assignment 

## Kent (AI/Map):

One of the problems that I ran into when making the zombie enemy was finding a skeletal mesh and model that had a large number of bones to fit the animation I was using. Eventually I realised that I wouldn't be able to find one without paying, so I had to work around using a model with less bones. This lead me towards Animation Retargeting (IK Rigs and IK Retargeters) which esentially made you select bones on one model (The low bone zombie model) and assign them to bones on a high bone model. A lot of animation tweaking later and I was able to use higher quality animations for my lower quality zombie skeletal mesh. This idea of retargeting higher quality models and animations into lower quality ones was a great skill to learn and will help me greatly in the future. 

Another new part of Unreal I learnt was the creation of AI with Blackboard and Behavour Trees behaviour. This system involved giving AI 'tasks' which it would switch between depending on the situation. This took a while to get to work the way I wanted, as I had to account for factors like if the enemy could see the player, if they could path to them, or if they were already attacking. Using decorator nodes as conditions helped account for these situations, and I eventually decidied on the tree of:

Roaming to a random location -> Waiting -> Loop

[If See Player and can Path To Player] Chase Player

[If Within Attack Range] Attack Player -> Rotate to face player

[If Still Within Range and Facing Player] Attack again -> Rotate to face player

[Otherwise] Chase Player


## Ocean (UI / Inventory):

Solo reflection on your part of the assignment 






