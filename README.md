# Geeetech A10M Chimera mod
A guide on how to install an E3D Chimera hotend on the Geeetech A10M, A20M, A30M and how to apdat other boards fro dual extrusion.


# Summary

[Introduction](https://github.com/Keybored02/Geeetech-A10M-Chimera-mod#introduction)

[1.0: Reliable is not in the Chinese vocabulary](https://github.com/Keybored02/Geeetech-A10M-Chimera-mod#part-10-reliable-is-not-in-the-chinese-vocabulary)

[1.1: Solutions?](https://github.com/Keybored02/Geeetech-A10M-Chimera-mod#part-11-solutions)

[1.2: A 1-in-1 mod](https://github.com/Keybored02/Geeetech-A10M-Chimera-mod#part-12-a-1-in-1-mod)

[2.0: A 2-in-2 mod]()

[2.1: The board is the limit]()

[2.1-bis: The breakout board]()

[3.0: The idyllic scenario: wiring of a populated board]()

# Introduction

I purchased my A10M for Christmas, with the intent of modding it to print dual materials at different temperatures (a thing quite hard on the stock model, as it has only one heating cartridge for both, forcing the tempertaure to fluctuate between the melting points of the 2 of them). I soon realized that the Cyclops-style hotend is not ideal if you’re printing with only one filament: melted material was flowing back through the other bowden tube, retraction was uneffective, oozing and stringing was unbereable. So, I decided that enough was enough.
I had two objectives:
1. Getting the printer to print reliably (spoiler, I can't)
2. Upgrade to a 2-in-2 Chimera hotend (for cheap)


# Part 1.0: Reliable is not in the Chinese vocabulary

Let's talk about the "original" 2-in-1 hotend. Inspired by the E3D Cyclops, its an all-metal design with a single heating cartridge, a NTC-100k thermistor and an M7-threaded nozzle. As far as I know, Geeetech produced 2 iterations of this extruder: the only difference is the heatsink design, the rest remains unchanged.

![Hotend Comparison](hotend_comparison.jpg)

Geeetech implemented a few flaws in their design. First of all, anti-backflow disks. Tiny pieces of metal located between the heatbreak and the heatblock that supposedly prevent molten filament from climbing up the other throath. Not only they do not work (I still got a clogged bowden), but they even limit retraction. In my experience, removing them changes very little. **NOTE: Factory firmware limits the retraction to 25mm/s, no matter the slicer's settings**

![disks](disks_closeup.jpg) ![disks](disks_position_1.jpg)


The other big issue is the amount of glue that holds all the screws on the heatblock and the heatbreaks themselves. In order to unscrew them, you have to heat them up at around 450°C with an heat gun. Otherwise, you'll just dent them (as shown in the image).

Now, let's talk about the flaws that are not Geeetech's fault. The 2-in-1 Cyclops (even the original one) hotends are not designed to print with a single filamnet, but always with two. If you're experiencing unwordly oozing and stringing with only one filament, there's not much you can do. The following diagram explains it (it's theoretical, not checked or supported by anyone other than me):

![Hotend Diagram](Hotend_Clog.png)

Consider also that the main difference between this and, let's say, a V6 hotend is the number of rigth angles that the filament has to go through before being extruded, and the fact that the length actually exposed to heat is bigger in the 2-in-1 (as the filament flows parallel to the heating cartridge, rather than perpendicularly), making it more similar to a Volcano hotend. Both of this elements need to be kept in consideration in our case.


# Part 1.1: Solutions?

Altough this is pretty much unfixable (as it is a structural flaw), we can still do something to mitigate the issue:
1. Printing with 2 filaments at any given time. They can be of the same color (two identical spools at 50-50%), or different . While extruding 2 filaments you're also retracting from both sides, mitigating the aforementioned oozing. **NOTE: Materials of different colors can have different printing temperatures due to the pigments they incorporate.**

2. Sticking a piece of filament into the unused heatbreak. Make sure that the printing temperature of this one is substantially higher than the one of material you'll be printing with.

3. Giving up color mixing (explained further later).


# Part 1.2: A 1-in-1 mod

The solution is a 1-in-1 or 2-in-2 mod. That's it. The design is flawed? Change the design.

Let's start from the easiest one, the 1-in-1. Assuming that you already have the 2-in-1 hotend, what you need is a V6 heatblock:
* [Original V6 Heatblock (incompatible with the stock thermistor)](https://e3d-online.com/products/v6-heaterblock-for-sensor-cartridges)
* [Clone (compatible, select the unofficial one)](https://it.aliexpress.com/item/32849595265.html?spm=a2g0o.productlist.0.0.289a21c5BJL6ka&algo_pvid=2ea0c950-dbdc-4134-aab4-0d17e1c7d871&algo_expid=2ea0c950-dbdc-4134-aab4-0d17e1c7d871-7&btsid=2100bdd016128109868592368ecdc2&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_)

By using the unofficial clone you can keep the awful stock thermistor and the heating cartridge. You'll still have to change the nozzle, as Geeetech uses an M7 threading, and the V6 family uses M6. My personal suggestions:
* [E3D original](https://e3d-online.com/products/v6-nozzles)
* [Trianglelab (unofficial)](https://it.aliexpress.com/item/32965509920.html?spm=a2g0o.detail.100009.2.1ced540ek9SFEo&gps-id=pcDetailLeftTopSell&scm=1007.13482.95643.0&scm_id=1007.13482.95643.0&scm-url=1007.13482.95643.0&pvid=48714b26-6e22-44f8-85ef-789399836e91&_t=gps-id:pcDetailLeftTopSell,scm-url:1007.13482.95643.0,pvid:48714b26-6e22-44f8-85ef-789399836e91,tpp_buckets:668%230%23131923%23100_668%23888%233325%235_668%232846%238113%231998_668%232717%237563%23523_668%231000022185%231000066059%230_668%233480%2315683%23647)

Since you are already at it, why not upgrading it to an hardened steel one?

Now that you have all you need, you can unistall the 2-in-1 following [this guide](https://github.com/caesar1111/Geeetech-A10M-HotEnd-Maintenance/blob/master/A10M_HotEnd_Maintenance.md). The assembly of the heatbreak-heatblock(V6)-cartridge-thermistor is really straigthforward, and I won't cover it here. What I will cover instead is the heatsink placement:

* dual heatsink (silver): use only one heatsink, insert the previously assembled block, align the indentation and screw in the heatbreak. Install the fans on the two sides. Screw the heatsink to the cage using the central holes (as shown in the picture).

![Silver Heatsink](silver_heatsink_placement.jpg)

* Single heatsink (black): in order to fit in the cage, you need to remove one of the two metal shields at the bottom. Assemble the block, screw the heatbreak, mount only one fan above the remaining metal shield. Screw the heatsink to the cage using the central holes (as shown in the picture). You can attach the second fan externally using some zipties. I don't recommend leaving the entire work to only one fan, since the thermal mass is considerable and the flow would cover only one side.

![Black Heatsink](black_heatsink_placement.jpg)

The end result should look really similar to an [A10 hotend](https://www.geeetech.com/geeetech-a10-a30-a30-pro-a20-3d-printer-24v-printing-head-p-1041.html).

Now that you have downgraded your A10M to an A10, lets' fix a couple of things: 

1. Level the bed.
2. Flash Marlin 2.0.x. You can follow [this video](https://www.youtube.com/watch?v=J14uJEd4XLU), but there are also many others that you can find. Besides all the cool new features, you'll also get the ability to actually change your retraction settings. The 1-in-1 mod doesn't require specific changes. If you already have Marlin 2.0 on your board, no re-flash needed.
3. PID tuning. Since you've changed the thermal configuration of the hotend, a PID tuning could be helpful if you are seing the temp readings fluctuate. Keep in mind that the thermistor is pretty inaccurate....[Video](https://www.youtube.com/watch?v=h9Rdid-T-Gw)
4. Calibration tests and benches. Run everything again: retraction and stringing tests, linear advance calibration etc.

# Part 2.0: A 2-in-2 mod

Color mixing surely it's cool, but it's also a limiting factor that prevents the printer from getting consistent, single-extruder results. While going 1-in-1 as explained in Part 1.2 solves the issue, it's more of a downgrade than an improvement. You paid for two extruders, you have to use both of them!.
You can get a Dua Extruder set up quite easily with the help of the E3D's Chimera+, which is basically a heatsink with two hollowings for two separate haetbreaks. It's integrated in the V6 ecosystem, so you can use the block and nozzles from a normal V6 hot end (heatbreaks are different). 

![Chimera+ original](Chimera+_E3D.jpg)

You can get the Chimera 
* [E3D Original](https://e3d-online.com/products/chimera)
* [Trianglelab clone](https://it.aliexpress.com/item/32908238691.html?spm=a2g0o.store_pc_allProduct.8148356.9.77b627c6nWPtjm)

A couple of considerations on the Trianglelab's clone: it's machined precisely, and I've had no problems adapting it to the Chimera+ CAD designs. Avoid extremely cheap off-brand clones (we'll talk about this later).

# Part 2.1: The board is the limit

If you're asking yourself: can I adapt my A10M/A20M/A30M/any printer to DualEx? The answer is: yes, at one condition. Your board must come with an header for a second thermistor and heating cartiridge. What follows is a rant on the status of Geeetech boards.

![GT2560 v4.0](GT2560_v4.0-100.jpg)

Up is a GT2560 v4.0 board used in the latest A10Ms and sold on the Geeetech store. Notice anything wrong? The traces for the Heater 1 (HE1) and Heater 2 (HE2) are not populated, while Heater 0 has only the MOSFET, withouth the connector. With this configuration, there's space only for one heater (which is already in use). If they already have the traces layed, why not using them? I'm sure that is not an unbearable expense to add a few connectors and SMD MOSFETs. You wanna know how I know that? Because on previous models, manufactured in 2019 and earlier (like the one I have), all traces are populated (image pulled from the [official forum](https://www.geeetech.com/forum/viewtopic.php?f=18&t=69799&start=30)).

![GT2560 v4.0 populated](GT2560_V4.0_populated.jpg)

This happens on other Geeetech boards too, across all models. 

# Part 2.1-bis: The breakout board

A couple of additional considerations:
- The Molex connector that links the mainboard to the breakout board on the back of the X-axis carriage is a total mess. Albeit showing 4 headers labeled heater, they're not actaully separated. They are wired in serially. In other words, it's just one line split across 4 ports. This puts a tremendous load on both ends in case 4 heaters are connected. Fire safety is a joke, isn't it? We cannot add a second extruder using that, it would be like duplicating the first. ![Breakout board](breakout_board.jpg)
- What just said applies to fan and temp sensors too: it's one line, duplicated to two headers. If you run the math, it does add up: the breakout board's Molex is 2x6, so 12 pins. 6 less than what the mainboard has. Wired in are 2 pins for the HE0, 2 for the temp sensor, 2 for a constant fan and 2 for the PWM fan, 4 for the BLTouch probe (one common ground). Total = 12 pins. There's no space for other lines.
- On the mainboard side, the 2x9 connector is actually wired to HE1 and HE2, as well as T1 and T0 (labeling for thermistors). But wait a minute, if HE0 is actually what we're usig (and we know it's connected), why doesn't the 2x9 list it? And why does it say that it connects to HE2, but not T2? It's piloting a heater without feedback? It's probably just a typo in the schematic, but remains extremely confusing. ![breakout schematic](breakout_schematic.png)
- **IMPORTANT:** The connector on the board is an alternative to the on-board connectors. It's wired in parallel to the HE0, HE1, T0, T1, Fan, BLtouch pins. In practical terms: you either use the connectors on the mainboard **OR** the ones on the breakout, because thy're the same thing for the microcontroller. Wiring two separate heaters, one to the HE0 connector on the breakout board and one to HE0 on the mainboard it's a big no-no. Same thing applies to the fans, thermistors, and BLtouch of course.

# Part 3.0: The idyllic scenario: wiring of a populated board

In order to proceed with the mod, you'll have to open the hood and look at your board. If it has all the connectors installed, good. Keep on reading.
If it doesn't, jump to Part 4.0

First of all, a BOM of the parts:
[Chimera+ Kit](https://it.aliexpress.com/item/32907340102.html?spm=a2g0o.store_pc_allProduct.8148356.3.77b627c6nWPtjm) that includes:
                          - Chimera+ heatsink and couplers
                          - 2x Kraken (unofficial naming) heatbreaks
                          - 2x ATC Semitec 104GT-2/104NT-4-R025H42G thermistor (cartridges, no glass beads)
                          - 2x 16mm, 24V 40W V6 heating cartridges
                          - 2x V6 heatbreaks
                          - 2x V6 0.4mm nozzles
                          - 3010 24V fan
                          - Not included, but recommended: - 2x Silicon socks
                                                           - 5015 24V fan 
                          - Additional hardware: - 3x M3 10mm screws
                                                 - 1x 20mm M3 nut and bolt (to hold the part fan)
                                                 - Zip ties
                                                 - Printed adapter plate
                                                 - Printed fan duct
You can purchase it as an assembly ready kit or mix match different parts, but this are the essentials. As mentioned prevoiusly, it's part of the V6 ecosystem.
You'll also have to print an adpater plate to mount to the carriage, and a fan duct

Now that you have everything, let's start.

- **Disassemble the X-axis carriage:** With the printer powered off and disconnected from the outlet, remove the fan shroud, disconnect the 2x6 Molex, remove the breakout board cover (two hex screws on the back of the carriage), and then unscrew the nuts that hold the wheels in place. Disconnect the heater cables, thermistor cables, and part cooling fan.
- **Assemble the Chimera:** Follow the [instructions](https://e3d-online.zendesk.com/hc/en-us/articles/360016354698-Chimera-Air-cooled-Assembly-Edition-1-)
- **Adapter mount:** I've designed a mount that is available on [Thingiverse](https://www.thingiverse.com/thing:4795634). You need 3x M3 10mm screws to screw in the Chimera, and you can reuse the factory screws to mount the plate to the carriage.
- **Wiring and cable management:** This is not as hard as it seems. Decide which one is Extruder 1 (usually the one on the left), and wire its heater to HE0 and its sensors to T0. Again, use the board connectors. If you have them , crimping ferrules for the haeter's cables are a good idea to add. Polarity doesn't matter (there's not defined + or -). For Extruder 2 use HE1 and T1. Pass the cables trough the cable slots on adpater plate and the carriage. You can bundle the cables in the Molex connector's sleeve or zip-tie them on the exterior. Make sure thy're not strained or under tension.
- **Fans:** I recommend using this new fan duct with a 5015 fan from [Thingiverse](https://www.thingiverse.com/thing:2175956/files). Th fan dcut is mounted on topo of the 3010 fan, using the included self-tapping screws. Be careful to tap in a straigth line. Reconnect the heatsink and part fans on the back of the board (follow the aforementioned diagram) and level the heigth of the fan duct.
                       



