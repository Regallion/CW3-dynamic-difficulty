A set of scripts for making a dynamic difficulty map. Explanations for input parameters for various scripts are in comments within the scripts. 
For mapmakers:
To setup the map, assign the images to slots as in the example map. Create a CRPLcore unit and assign to it the script "ManagerScript.crpl". Create another core with "SpawnDirector.crpl". Create another core and add to it "ChunkManager.crpl". Move the first couple of cores off-map.
This creates the basis for the map, those scripts ensure that the custom managers know where the player's units are and how developed his position is.
To have an actual effect on the gameplay, add several (as many as you like) scripts to create various nastiness. Those should be on separate off-map cores.
1. "Backdoorer manager.crpl" - generates portals in places where there is little military and no creeper.
2. "Harasser manager.crpl" - generates portals around places with high economic activity (reactor farms, unsecured collector grids)
3. "SweeperManager.crpl" - generates UFOs to attack frontline military.
4. "VortexManager.crpl" - generates creeper vortices around the map. Those erupt into spores and are generally disruptive.
5. "DisruptorManager.crpl" - generates timebombs on unsecured relays and collectors.
6. "EnemyManager.crpl" - scales enemy emitters and spore towers with the scaling factor. Also redistributes production from destroyed units to surviving ones.

Tips:
When deciding on Chunk size, keep in mind that a map should be roughly 15 chunks across. If your map is very irregularily shaped (like 5x200) this script will behave weirdly. However, the chunks should not be less than 2 units across for the same reason.
Chunks are X-sided squares around the auto-generated core. The cores perish on recompile so don't be too worried if you accidentally move or delete one.
THe set of unit and potential weights is something you need to decide on yourself. They vary with the map and the chunk size. A good estimate is that a basic base which is barely resisting creeper should be around 4 on the scaler. This is, however just a suggestion..
The included Clickjacker.crpl scripts advances the RNG whenever a player clicks. Only use it if you want to make the map extra unpredictable.
The script set is designed to be modular - you do not need to use all the managers and you can even write your own custom ones.
If the chunk's core is located over void, this chunks is disabled. Enemy units from the base script set will not spawn in it. However, when using large chunks (over 10)with their center just on the edge of a void, there is a chance of a backdoorer spawning outside of nullifier range. Keep that in mind.
