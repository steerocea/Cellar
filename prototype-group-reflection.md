# Prototype Group Reflection 

Overall we believe as a team we worked well together to get this prototype and working by the deadline. Of course being a smaller group of only 3 comes with its challenges especially when working with deadlines, significant amounts of work, and also other university projects on the side, however, through our effective communication and work delegation we made it work and work well. 

## Levi (Weapons):

Overall the implementation of the weapons was not too difficult but many parts of it were still very time consuming such as trying to find sword models that would work for our game aswell as learning many mechanics that I had not used before such as the animation system. My work involved creating a weapon asset and allowing the player to pick it up and use it to damage an enemy. This required me to learn how to create animations and how to implement them into the state diagram for animations which would allow the player to go back to idle or running animations after the swing was finished. I also learnt a bit about line casts with vectors which I used to find wher the player was looking in order to deal damage.

Another thing that I learnt whilst creating the prototype was how best to work with the others including how to properly use gitlab as this is a fairly new experience for me. I had to get help with merging and dealing with changes at first but i am now feeling more confident in my abilites. I also had to make my weapons interact with the enemies that i had not created which required me to read through those blueprints and base the damage dealing and enemy detecting on how the enemy worked. The weapons that i create also need to be compatable with an inventory system so i made sure to include functions for equip aswell as unequip in order for it to be easy to do from the inventory. 

## Kent (AI/Map):

One of the problems that I ran into when making the zombie enemy was finding a skeletal mesh and model that had a large number of bones to fit the animation I was using. Eventually I realised that I wouldn't be able to find one without paying, so I had to work around using a model with less bones. This lead me towards Animation Retargeting (IK Rigs and IK Retargeters) which esentially made you select bones on one model (The low bone zombie model) and assign them to bones on a high bone model. A lot of animation tweaking later and I was able to use higher quality animations for my lower quality zombie skeletal mesh. This idea of retargeting higher quality models and animations into lower quality ones was a great skill to learn and will help me greatly in the future. 

Another new part of Unreal I learnt was the creation of AI with Blackboard and Behaviour Trees. This system involved giving AI 'tasks' which it would switch between depending on the situation. This took a while to get to work the way I wanted, as I had to account for factors like if the enemy could see the player, if they could path to them, or if they were already attacking. Using decorator nodes as conditions helped account for these situations, and I eventually decidied on the tree of:

Roaming to a random location -> Waiting -> Loop

[If See Player and can Path To Player] Chase Player

[If Within Attack Range] Attack Player -> Rotate to face player

[If Still Within Range and Facing Player] Attack again -> Rotate to face player

[Otherwise] Chase Player

I also started on the early implementation of the Procedural system, where I have hallways that can branch into three directions, but randomly choose if which ones they do. This then iterations for the 'number of iterations' chosen. It currently has two hallway types, but in the future this will be the baseline to be extended and have many more hallways, added rooms, and other features.  


## Ocean (UI / Inventory):

Overall the setup and execution of the inventory / chest system went relatively smoothly thanks to the abundance of online resources covering the topic. Although, there were still many difficulties in the process that came with the intricacies of so many different blueprints intertwining and working with each other. 

In particular getting lost within the happenings of each blueprint especially in the more robust ones such the InventorySystem and InventoryComponent, knowing when and where to use it variable also became quite the difficulty such as which inventory is currently being access (chest or player) and updating the inventory accordingly such as when an item is dragged and dropped out of a chest. To solve this issue I added grouping and comments to blueprints that were particularly robust and confusing. Some challenging calculations were also made around stacking items on top of each other and accounting for overflow and stack size, as well as swapping positions with items not sharing the same ID when using the drag and swap. 

Overall, I am very happy with the way I have set up the inventory system which is in a way that will make it easily expandable due to features such as the data table allowing us to easily add new item as well as new variables such as potential item stats / abilities. My next step for this system building off the prototype would be to implement an equipping and use system allowing armour and weapons to be equipped to the player and consumables to be used with their effects being activated







