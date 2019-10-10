# Clumping

<iframe src="https://player.vimeo.com/video/358842309" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>

Single-Network Training. Simulations run with this model display similar behaviour. Agents tend to clump around a specific section of the planet, and move together in the same direction. This may be due to them sharing replicas of the same network, and would therefore see similar Q-values for their actions. Of note is that any Agents that separate from the group tend to die fairly quickly (See 0:20 in video) . Finally, when a McGuffin is added to the scene, Agents in this model begin attacking other Agents (See 1:40 in video). This is very close to the narrative drama that we were hoping to find in the simulations

One last thing of note is that we removed the survival and balancing rewards for this training example. Here, Agents are only rewarded while nurturing the McGuffin.

Reward Function:
- +1 for each frame consuming
- -100 on death

# Playing Chicken

<iframe src="https://player.vimeo.com/video/358820441" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>

This was one of our first approaches at a multi-network system. We were quite surprised when a majority of the training samples showed a single Agent on the planet. This experiment originally started as a strategy to spread out. This Agent learned to run from other Agents, and wait for the others to fall, before running a mad dash in order to survive.

Reward function
- -1 for falling off the planet
- +0.1 each frame for staying on
- +0.1 (additional) per frame if the planet’s angular velocity is slower than the last time reward was calculated


# Dancing and afraid

<iframe src="https://player.vimeo.com/video/358836669" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>

This is one of our last attempts at Single-Network Training.
Agents Seem to dance around the top of the planet. Placement of the McGuffin causes them to stop dancing, and clump together in "fear".  They then step away from the McGuffin slowly.

Reward function:
- +.1 per frame for surviving
- +.1 per frame for slowing down the planet (reducing angular speed)
- -1 on death
- +1 per frame during a consume state

# Fight Club

<iframe src="https://player.vimeo.com/video/358939948" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>

Another Multi-Network Simulation
This experiment rewards Agents solely for consuming the McGuffin. Agents in this simulation are a lot more aggressive, and start the simulation off by fighting consistently. One of the flaws of our current simulation approach is that the Agents who do not learn to survive have less experience to train on. We can see this in the Agent that throws itself off of the planet every time. Agents here have learned to consume the McGuffin in its seed state, but shy away from it once it grows. This is likely due to the weight influence that it has on the planet.

Two notes:

1) The springy animation of the Agents and the interlocking of their joints does not have an impact on their movement and actions. The Agents are still capsules that stand orthogonal from the surface of the world.
2) The pause that the Agents undergo when the McGuffin is being spawned is forced on the Agents

Reward function:
- +1 per frame for consuming
- -10 on death
