[First][first] | [Previous][prev] | [Next][next]


> And their appearance and their work was as it were, a wheel in the middle of a wheel.
> 
> _&mdash; Ezekiel 1:16_

--------

Matt collapsed back in his chair, defeated.
He'd been awake for 43 hours at this point, and he was essentially out of options.
If he wanted to have anything at all to show for in 8 hours at the competition, he needed to start the compiler now.

This year's undergraduate robotics competition involved autonomously navegating an underwater maze to retrieve a simulated submarine escape pod.

His responsibility had been designing the navegation system used to get to the pod, and he'd chosed to base the design on a species of pufferfish, _Torquigener tetraodontidae_, known for constructing [large circular geometric patterns][pufferfish] underwater in order to attract potential mates.
Neural simulations based on aquatic animals generally performed very well in this type of environment, and it stood to reason that this pufferfish might be especially suited due to it's apparent ability to process complicated geometric patterns.

[pufferfish]: doi.org/10.1038/srep02106

So far he'd been able to successfully abstract out the pufferfish's motor cortex and get it to control the UAV's thrusters, but no matter what he'd tried he hadn't been able to figure out it's visual cortex or sensory mechanisms.
He could potentially just simulate the pufferfish brain directly, but usually that took a lot of processing power, and he wasn't sure if the UAV's processor would be able to handle it.

At this point, he just had to hope the compiler would be able to optimize it enough to at least _work_, even if it couldn't run fast enough to be competitive.

Dejectedly, he set it running, and fell asleep in his chair.

--------

Matt awoke with a start to sunlight streaming in onto his face.
He checked the time - 12:30 - and started scrolled through his notifications before suddenly remembering he needed to be at the competition in 15 minutes.

He hastily grabbed the UAV and stuffed it in his bag with his laptop, only sparing a glance to ensure everything had compiled, before running as quickly as he could from the Computer Science Department to the Richards Building pool where the competition was being held.

"You got it figured out?" Jessica called to him as he arrived panting to the competition area.

"I ... I think so?" Matt gasped, trying to catch his breath.
The optimization report had said it had managed to fit the simulation onto the UAV's processor.
He pulled the UAV out of his bag and handed it to her.
"It will work, I'm pretty sure."

Jessica had been responsible for the mechanical design of the project, and she'd also been the one to who'd gotten him the neural scan he'd used as a basis for the programming.

"Mike messaged me and he should be here in - nnng there he is." she said, turning as she spotted Mike making his way through the light crowd.

Mike had done a lot of the electrical design, but more importantly he had also been the one who'd gotten most of their funding &mdash; apparently his uncle had made an absurd amount of money off the "bitcoin boom" in the thirties, and was only too glad to use some of it to help fund his nephiew's education.

"Hey we ready?" he asked once he'd gotten to them.

Matt nodded. "Let's go."

--------

It turned out, their UAV performed very well.
Well enough to win the competition.
And in fact, well enough that they had initially been suspected of cheating by hardcoding the maze or controlling it remotely.
(This was resolved by running it through a new, randomly generated layout, and examining the hardware to make sure there wasn't a reciever that would allow remote control.)
The UAV just zipped through the maze, following pretty much the idea route first time, and their time to retrieve the capsule came in just under _a third_ that of the next fastest team.

This was despite the fact that they had accidentally _dropped_ the UAV beforehand, and while Matt had hoped nothing too series had broken, the tinkle of glass from the camera had told him that was a lie.

His teammate's were overjoyed of course, and didn't really suspect anything was unusual, but Matt knew, they hadn't just done well, they'd done _impossibly_ well.

--------

Matt set the UAV on his desk and powered it on, before unzipping his bag to pull out the 3-d printed tile with the pufferfish ridges.
Immediately the UAV's thrusters spun up, and he zipped his bag shut to go shut it off, but as soon as he zipped it closed it shut off.
He opened the zipper a tiny bit.
Nothing.
Opened it a bit more, and immediately the thrusters spun up again until he zipped it back closed.

This was weird.

After disconnecting the thrusters (running them in air could potentially cause them to overheat) and wiring up a display, he pulled the tile back out.
As he had kind-of expected by this point, the display immediately reacted, and as he moved the tile around the display readout changed to match the direction to the tile.

He continued disconnecting various components, trying to isolate the cause.
He quicly eliminated the (broken) camera and the acoustic sensors, and after a few minutes all hea had left was the bare processor board, attached to the power supply and the display.
Still the display consistently read out the direction to the tile.

This was _very_ weird.

--------

He spent the rest of the weekend going through the software and eliminating pieces.
The pufferfish neural simulation appeared to be a nessisary component, but he had eliminated nearly everything else that wasn't in some way required to run that simulation.
Frustratingly, it would also stop working any time he tried logging the simulation to a file.
After systematically paring down the neural simulation, he was left with a cluster of about 40 neurons that appeared to be responsible for this behavior.
And none of them were even distantly connected to any of the sensory corticies.

--------

After a week of working on this, he had learned a number of things about the effect.

The effective range of the effect was limited to around 10 meters. Outside of that, the reliability would start to tail off, and he wouldn't be able to consistently detect and locate the tile.

Additionally, it turns out that some types of plastic (like polyethylene or polystyrene) block the effect (although others, like nylon and polyester, had no effect).
But more than that, assuming there was still a clear path, the reading would actually deflect _around_ any impeding plastic material.
This particularily explained how the UAV was able to traverse the maze so efficiently, as the obstacles had been made of polyethylene sheeting.

But most importantly, he learned that the pattern he had on the tile didn't need to be 3-d printed:
He had taken a photo of the tile with his phone and was looking at it when he noticed the reading had changed.
Instead of pointing to the tile over on his desk, it was pointing to his phone, and the image displayed on it.

After having a proper black-and-white vectorized version of the pattern printed out (he'd had the first one laminated, but turns out the lamination blocked the effect).

Further experimentation with this effect led him to discover that the _smaller_ the pattern was, the further the effective range was, and that it depended very strongly on having accurate relative dimensions in the pattern.

And then he started optimizing it.
He set up an apparatus consisting of a polyethylene box with a servo-controlled shutter, with a display set up inside.
He'd found that a plastic box with a small enough opening would impede but not completely eliminate the reading, and he set up a computer to use this feedback to optimize the pattern and neural simulation.

After a week, he had to change out the display for a wireless tablet (the hole for the cable was now big enough to matter) and replace the plastic shutter with an optical diaphragm, since even with the shutter completely closed it was still able to detect the pattern.

After another week, he swapped it out for a 2-inch thick ultrasonically-welded plastic box with a microfluidics duct he could pump gasoline into to vary the effective thickness.

The next week, he sent out the design to be fabricated onto an IC. He only had enough money for an older GlobalFoundries 22FDX process, but it should be small enough.

--------

[First][first] | [Previous][prev] | [Next][next]

[first]: http://example.com
[prev]: http://example.com
[next]: http://example.com
