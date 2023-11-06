# Name
Levi Hawkins
HawkinLevi

# Role
Project Role - Weapons/Consumables
Animal Role - Owl

##Group Contribution:

#My Contribution
I was in charge of working on the weapons and consumables. I also filled the role of Owl throughout this project. This involved making sure the rules of our game were followed and also making sure that everything moved forward. This required me to ensure that any problems that arose that hindered the productivity of our game were resolved as quickly as possible. Obviously as our group was only 3 people for a 6 person model the animal roles did not work as effectively as there is not much organizational work that needs to be done.

#Group Dynamics
I think that our group worked very well together despite the fact that some of us were very busy during the semester. Because we only had 3 people it made communication between the group extremely easy and made it much easier to work on things without causing merge errors. I found that the discord was the most effective form of communication for our group as it allowed us to easily communicate the necsessary information and easily discuss our next steps. Overall the group worked very well together and there were no major hurdles caused by lack of communcation in the development of our game.

##Code Discussion
The primary part that I worked on was the weapons and the consumables. I did all of the work on these parts. The weapons that i implemented were: Short Sword, Long Sword, Bow and Health Potion. I had not worked with weapons or items in general before in unreal. As a result it is not the most efficient implemetation of the weapons however it still produces the same result. I implemented weapons by simply attatching all of the weapons to the player and making them invisible alongside a variable that decided if it could be seen or not. I then created an equip and unequip function for each that would do as its name suggests. I also created a function for each weapon that would attack. This did require me to work with some features that i had not worked with before such as raycasts. In order to create a wide swing for the Long Sword I used a for loop that would rotate the angle of the raycast and cast it multiple times in order to simulate a swing and I felt it would be more consistant than swinging a collider. I used the main first person player graph to create a decent chunk of my code as i needed to use delays which do not work in fucntions. The delays are used so that I could change how often the player can attack depending on the weapon aswell as allowing me to make sure the animations had time to play. When the player left clicks my code decides what weapon is equipped and then does the attack and plays the sound aswell as some other functions that add to the looks of my items. The animation is not done in this part though as it is done in the first person animation graph alongsinde the state diagram which uses tghe variables from the player to decide what animation should be played. I was also responsible for the characters ability to sprint which was simple based on the fact that i had done it for the previous project and the player movement built into the first person character makes it reasonably easy. 

#Interesting / Proud
The part that I found most interesting and also am the most proud of is my hit detection for the long sword attack. As previously mentioned it works using multiple raycasts spaced evenly apart based on an angle. It also has detection in order to assure that a single swing doesnt hit an enemy twice. I am proud of the part specifically as it took me quite some time as my first attempt was 3 hard coded rays that was bulky and ineficient. I decided to remake it when i tried to up the amount of rays to 5 as 3 left too larger gaps. I was planning on just adding more raycast nodes but it got too big and was hard to work with so i decided to remake it with a for loop

<img src="HawkinLeviImages/capture.JPG" width="800"/>

#Bad Code
When I started making the weapons it was easy with just the short sword and i thought the method of using the main event graph to do everything would work but as the weapons got more complicated and i added more of them it became just a massive mess of nodes that is rather hard to understand or work on. With this code i also just changed and added delays based on what I felt was appropriate which resulted in inefficient use of space and makes it much harder for anyone else to work with.

<img src="HawkinLeviImages/capture1.JPG" width="800"/>

#Chat GPT
As I was using nodes and not C++ I did not have to rely on chat gpt as it is not very usefull for newer version of unreal.

##What I Learnt
This assignment proved to be a valuable learning experience as I was introduced to new concepts and a different way of allocating group roles that forced me to take part in the organization of the team. The main things that I found that I learnt from this project was how to work with a group in unreal and how to work with animations and raycasts. For the first assignment in unreal it took me a long time to figure out how to use gitlab but with my experience from that assignment and help from my teamates with this one I feel much more confident in my ability to use gitlab without causing problems for my team. I also had to do quite a lot of animating as I created all of the animations for the weapon attacks myself which I had not done before. It took quite a lot of my time but i now have a decent understanding of the animation editor aswell as the state digram that controlls the animations.

#Going Forward
Seeing as most projects that I will work on in the future will most likely not be using unreal and probably not even involve a game the skill that I found most usefull from this class was the ability to work as a team using gitlab. Obviously I have had to use github to work with other groups before and I will have to use it with many more groups to come so the knowledge of gitlab that I aqquired from this assignement specifically will prove to be a valuable asset for my future projects.
