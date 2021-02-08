# Geeetech A10M Chimera mod
A guide on how to install an E3D Chimera hotend on the Geeetech A10M


# Introduction

I purchased my A10M for Christams, with the intent of modding it to print dual materials at different temperatures (a thing quite hard on the stock model, as it has only one haeting cartiridge for both, forcing the tempertaure to fluctuate between the melting points of the 2 of them). I soon realized that the Cyclops-style hotend is not ideal if you’re printing with only one filament: melted material was flowing back through the other bowden tube, retraction was uneffective, oozing and stringing was unbereable. So, I decided that enough was enough.
I had two objectives:
1. Getting the printer to print reliably
2. Upgrade to a 2-in-2 Chimera hotend (for cheap)


# Part 1.0: Reliable is not in the Chinese vocabulary

Let's talk about the "original" 2-in-1 hotend. Inspired by the E3D Cyclops, its an all-metal design with a single haeting cartridge, a single thermistor and an M7 nozzle. As far as I know, Geeetech produced 2 iterations of this extruder: the only difference is the heatsink design, the rest remains unchanged.

![Hotend Comparison](hotend_comparison.jpg)

Geeetech implemented a few flaws in their designs. First of all, anti-backflow disks. Tiny pieces of metal located between the heatbreak and the heatblock that supposedly prevent molten filament from climbing up the other throath. Not only they do not work (I still got a clogged bowden), but they even limit retraction. In my experience, removing them changes very little.

**NOTE: Factory firmware limits the retraction to 25mm/s, no matter the slicer's settings**

![disks](disks_closeup.jpg)

![disks](disks_position_1.jpg)

The other big issue is the amount of glue that holds all the screws on the heatblock and the heatbreaks themselves. In order to unscrew them, you have to heat them up at around 450°C with an heat gun. Otherwise, you'll just dent them (as shown in the image).

Now, let's talk about the flaws that are not Geeetech's fault. The 2-in-1 Cyclops (even the original one) hotends are not designed to print with a single filamnet, but always with two. If you're experiencing unwordly oozing and stringing with only one filament, there's not much you can do. The following diagram explains it (it's a theoretical hypotesi, not checked or supported by anyone other than me):

![Hotend Diagram](Hotend_Clog_Explained.png)

Consider also that the main difference between this and, let's say, a V6 hotend is the number of angles that the filament has to go through before being extruded, and the fact that the length actually exposed to heat is bigger in the 2-in-1 (as the filament flows parallel to the heating cartridge, rather than perpendicularly), making it more similar to a Volcano hotend. Both of this elements need to be kept in consideration in our case.


# Part 1.1: Solutions?

Altough this is pretty much unfixable (as it is a structural flaw), we can still do something to mitigate the issue:
1. Printing with 2 filaments at any given time. They can be of the same color (two identical spools at 50-50%), or different . While extruding 2 filaments you're also retracting from both sides, mitigating the aforementioned oozing. 
**NOTE: Materials of different colors can have different printing temperatures due to the pigments they incorporate.**
