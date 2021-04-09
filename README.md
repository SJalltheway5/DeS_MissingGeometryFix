# Demon's Souls - Missing Geometry Fix (RPCS3)

0.10 - 2021-04-09

This mod addresses most of the missing geometry in Demon's Souls when played on RPCS3 (https://github.com/RPCS3/rpcs3/issues/4302).  It is currently still a work-in-progress.

Huge thanks to Vahellis for the Demon's Souls modding tutorial (https://www.nexusmods.com/demonssouls/mods/21), and to TKGP, Wulf2k, horkrux, dropoff for the various tools and source code I learned from to make this possible.

Nexus Mods page: https://www.nexusmods.com/demonssouls/mods/39

### FIXED:

* Soldier's Shield
* Slave's Shield
* Spiral Rapier
* Brass Telescope
* Monk's Head Wrappings (3-3 cutscene)
* Dead Stormbeasts (4-2)
* Storm King's Projectiles (4-3)

### STILL MISSING:

* Dead miners in webs (2-1)
  * `map/m06_00_00_00/m0103b0.flver` includes bodies and the tunnel geometry leading to the Armor Spider
  * `map/m06_00_00_00/m0112b0.flver` includes bodies and webs at the bottom of the elevator leading to the Armor Spider
  * `map/m06_00_00_00/m0015b0.flver` includes bodies and map geometry (past the Fat Official)

* Fallen Heart (3-2)
  * removed collision geometry (object is completely gone, not just invisible)
  * the spot with a big chunk out of the floor can still be walked on
