Here are a few training videos with their associated setups and functions:

#### Playing Chicken
This was one of our first approaches at a multi-network system. We were quite surprised when a majority of the training samples showed a single agent on the planet. Originally starting as a strategy to spread out. This agent learned to run from other agents, and wait for the others to fall, before running a mad dash in order to survive.

Reward function
 - -1 for falling off the planet
 - +0.1 each frame for staying on
 - +0.1 (additional) per frame if the planet’s angular velocity is slower than the last time reward was calculated

<iframe src="https://player.vimeo.com/video/358820441" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>

#### Dancing and afraid

This is one of our last attempts at Single-Network Training.
Agents Seem to dance around the top of the planet. Placement of the Mcguffin causes them to stop dancing, and clump together in "fear".  They then step away from the mcguffin slowly. 

Reward function:
 - +.1 per frame for surviving
 - +.1 per frame for slowing down the planet (reducing angular speed)
 - -1 on death
 - +1 per frame during a consume state

<iframe src="https://player.vimeo.com/video/358836669" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>


#### Clumping

Another Single-Network Training. Simulations run with this model display similar behaviour. Agents tend to clump around a specific section of the planet, and move together in the same direction. This may be due to them sharing replicas of the same network, and would therefore see similar Q-values for their actions. Of note is that any agents that separate from the group tend to die fairly quickly (See 0:20 in video) . Finally, when a mcguffin is added to the scene, agents in this model begin attacking other agents (See 1:40 in video). This is very close to the narrative drama that we were hoping to find in the simiulations.

One last thing of note is that we removed the survival and balancing rewards for this training example. Here, agents are only rewarded while nurturing the MacGuffin.

Reward Function:
 - +1 for each frame consuming
 - 100 on death
