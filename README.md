# ErgoChoco-PCB
 My first PCB - a de-split split layout taking my favorite design details from the Corne, Kyria, Absolem, and others.

## The name
 I'm an engineer, and true to form I'm bad at naming things. I'd heard the ErgoDox was designed by a user named Dox, and my handle is Choco617, so: ErgoChoco.
 
## Layout explanation:
I love my Corne, but I quickly found that I always orient the halves the same way, making the actual separation and the TRRS cable more of a nuisance, much as I love the concept. So I experimented with angles and settled on 30°. I had also always wondered if I would like more columnar stagger: the Corne seems pretty conservative on that. So after reading the Kyria design log, I took the same approach, made some measurements of my own fingers’ natural resting positions, and discovered they were negligibly different from the Kyria’s, so I lifted those columnar stagger dimensions wholesale. I love the look of the 1.5U thumb keys on the Corne, but I admit it’s always been annoying for keycap compatibility that they prevent me from just getting a Planck set, so I replaced the 1.5U keys with 1U. I set the hands just far enough apart to fit a Pro Micro between them. A cardboard prototype with leftover switches/caps stuffed into it confirmed that was a comfy layout for me (and the all-1U thumb arcs don’t look as bad as I worried they would).

## Design Priorities:

### PCB
- Kailh hotswap sockets (direct soldering not supported: I'm the only intended user, so I can do what I want :P)
- In-switch LED (with Holtites so that it doesn't defeat the purpose of switch hotswap)
- South-facing switches (I like seeing the LEDs right up front)
- Pro Micro. I originally designed this with an onboard MCU, then decided I would rather keep all the complicated stuff on a Pro Micro to keep the PCB simpler/cheaper and allow me to replace the controller if something awful happened. Also, Pro Micro instead of Elite-C just because I already have micro-USB cables. The Pro Micro is socketed anyway, so I can always change later if I feel like it.
- SMD all the things (mostly diodes/resistors). I wanted to see if I could actually solder all of it myself, and I like the idea of keeping everything as small as possible, and technically minimizing EMI.
- Ground plane everywhere. My original Contra was very prone to ESD shocks, so in the original onboard-MCU version of this PCB, I had an ESD protection circuit with a PRTR5V0U2X. Now with a Pro Micro design, the best I can do (I think) is extensive ground planes and connecting the mounting holes to them so the PCB is grounded to the stainless steel case. I'm a mechanical engineer, not an electrical engineer, so I hope this is sufficient.
- Breakout pads for GND/+5V/F4 data pin to allow RGB underglow (inspired by the Contra). Not sure where I would physically fit an RGB strip, since I intentionally designed no gap under the PCB, but it seemed silly not to include this while I was designing the PCB, since I had the pin available.

### Case (dedicated repo: [https://github.com/Choco617/ErgoChoco-case](https://github.com/Choco617/ErgoChoco-case))
- Stainless sandwich/skeleton case. Top and bottom plates have a perimeter of 8mm aluminum standoffs around the edges of the PCB. I've used this in previous boards, and I love the look.
- Bottom plate mechanically supports hotswap sockets from behind. It annoys me that switch-swapping in my sandwich-case Corne requires me to disassemble everything so I can hold the sockets firm when I insert the new switches, so this case is designed so that the bottom plate (through a layer of non-conductive gasket) contacts the sockets. The PCB is bolted to the bottom plate to keep this secure.
- Minimal height. Without resorting to low-profile switches, I want to keep the plate height as low as possible, mainly for aesthetics and comfort reasons, but also because it's mechanically necessary in order to let the bottom plate contact the backs of the hotswap sockets.
- Pro Micro installation on PCB: to minimize height but still keep the Pro Micro under the plate (I don't like them exposed like on the Corne), the PCB has a U-shaped relief at the Pro Micro footprint. The Pro Micro is installed component-side down on the top of the PCB so the USB port hangs down into that relief.
- Case structure as a result of these choices: PCB is bolted to the top of the bottom plate, with a gasket layer (just vaguely compressible rubbery drawer liner, nothing fancy) in between for electrical insulation, then standoffs are bolted to the top of the bottom plate around the PCB, then the top plate is bolted to the standoffs, then switches are inserted.

