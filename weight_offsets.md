# Demon's Souls (2009)
## bone weight offsets

|object|file|FLVER|mesh|offset|vertices|vert length|
|-|-|-|-|-|-|-|
|Soldier's Shield|`parts/wp_a_1509.partsbnd.dcx`|`WP_A_1509.flver`|1/1|`0xC90`|235|`0x28`|
|''|`parts/wp_a_1509_l.partsbnd.dcx`|`WP_A_1509_L.flver`|1/1|`0xCB0`|235|`0x28`|
|Slave's Shield|`parts/wp_a_1511.partsbnd.dcx`|`WP_A_1511.flver`|1/1|`0xBD0`|159|`0x28`|
|''|`parts/wp_a_1511_l.partsbnd.dcx`|`WP_A_1511_L.flver`|1/1|`0xBB0`|139|`0x28`|
|Spiral Rapier|`parts/wp_a_0351.partsbnd.dcx`|`WP_A_0351.flver`|1/1|`0xB30`|162|`0x28`|
|''|`parts/wp_a_0351_l.partsbnd.dcx`|`WP_A_0351_L.flver`|1/1|`0xB50`|162|`0x28`|
|Brass Telescope|`sfx/ds_sfxbnd_commonresources.ffxbnd.dcx`|`s3031.flver`|1/1|`0xA10`|472|`0x28`|
|dead miners (2-1)|`map/m06_00_00_00/m0015b0.flver.dcx`|`m0015b0.flver`|1/8|`0xED30`|8244|`0x28`|
|''|''|''|2/8|`0x62170`|1876|`0x28`|
|''|`map/m06_00_00_00/m0103b0.flver.dcx`|`m0103b0.flver`|1/9|`0xFE50`|12366|`0x28`|
|''|''|''|2/9|`0x8C3D0`|3519|`0x28`|
|''|`map/m06_00_00_00/m0112b0.flver.dcx`|`m0112b0.flver`|1/3|`0xB410`|9618|`0x28`|
|''|''|''|2/3|`0x6C090`|2798|`0x28`|
|fallen heart (3-2)|`map/m04_01_00_00/m3107b1.flver.dcx`|`m3107b1.flver`|15/18|`0x85B30`|911|`0x2C`|
|''|''|''|16/18|`0x8FF10`|450|`0x2C`|
|''|''|''|17/18|`0x94D90`|52|`0x34`|
|''|''|''|18/18|`0x95ED0`|558|`0x2C`|
|Monk's Head Wrappings (3-3)|`sfx/ds_sfxbnd_commonresources.ffxbnd.dcx`|`s0200.flver`|1/1|`0x1B70`|840|`0x28`|
|dead stormbeasts (4-2)|`obj/o3480.objbnd.dcx`|`o3840.flver`|1/1|`0x6DB0`|4080|`0x28`|
|Storm King's projectiles (4-3)|`sfx/ds_sfxbnd_commonresources.ffxbnd.dcx`|`s3025.flver`|1/2|`0x990`|120|`0x28`|
|''|''|''|2/2|`0x1FF0`|233|`0x28`|

`*.flver` files were patched by:
* opening the file and seeking to the specified offset for each mesh
  * this is the location of the first bone weight of the first vertex
* writing two bytes (`0x7FFF`)
* seeking to the next vertex (vert length - `0x2`)
* repeating for each subsequent vertex in the mesh

```
// open file
// go to offset
for (currentVertex = 1; currentVertex <= totalVertices; currentVertex + 1)
{
  // write 0x7FFF
  // skip ahead by the vertex length - 0x2
}
// close file
```
