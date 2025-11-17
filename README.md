# GAME_PROGRAM-EX--5
# Making Player to collect the ammo and increase the bullet spawn count.

# Aim
To implement a gameplay feature where the player collects ammo pickups in the game world. Upon collecting ammo, the player's ammo count increases, enabling more bullet spawns (shots).

# Procedure
# 1. Setup Player Character
      Open your PlayerCharacter Blueprint.s
      Add a new Integer variable named AmmoCount.
      Set an initial default value (e.g., AmmoCount = 10).
      Ensure you have a shooting mechanism in place that uses AmmoCount to determine if a bullet can be fired.

# 2. Create Ammo Pickup Blueprint
      Go to the Content Browser → Right-click → Blueprint Class → Select Actor → Name it BP_AmmoPickup.
      Add components:
          Static Mesh: Representing the ammo (e.g., a bullet or crate).
          Sphere Collision: To detect overlap with the player.
      In the Event Graph of BP_AmmoPickup:
          Use OnComponentBeginOverlap on the Sphere Collision.
          Cast to PlayerCharacter.
          Increase the player’s AmmoCount (e.g., AmmoCount += 5).
          Optionally, play a pickup sound or effect.
          Destroy the ammo pickup actor.

# 3. Update Shooting Logic (Optional)
     In your player’s shooting logic:
        Before spawning a bullet, check if AmmoCount > 0.
        If true:
             Spawn bullet.
             Decrease AmmoCount by 1.

# 4. Place Ammo in the World
       Drag instances of BP_AmmoPickup into your level from the Content Browser.
       Adjust position, mesh, and pickup range as needed.


# Output

<img width="562" height="248" alt="image" src="https://github.com/user-attachments/assets/101e12e3-d26e-43d2-be1e-4fdd0a5ec866" />

<img width="559" height="349" alt="image" src="https://github.com/user-attachments/assets/3c8e25a8-3178-431e-818b-7a26b96c9871" />

<img width="562" height="293" alt="image" src="https://github.com/user-attachments/assets/b230bbd3-3636-419e-9807-3dec71b66222" />

<img width="559" height="370" alt="image" src="https://github.com/user-attachments/assets/3a691672-7e54-468a-be19-95693c509454" />

# Result
   The player starts with a limited number of bullets.
   When the player overlaps with an ammo pickup:
         The ammo is collected.
         The player's AmmoCount increases.
   The player can now fire additional bullets based on the updated ammo count.

