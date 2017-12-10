
> And their appearance and their work was as it were, a wheel in the middle of a wheel.
> 
> _&mdash; Ezekiel 1:16_

--------

Matt collapsed back in his chair, defeated.
He'd been awake for 43 hours at this point, and he was essentially out of options.
If he wanted to have anything at all to show for in 8 hours at the competition, he needed to start the compiler now.

This year's undergraduate robotics competition involved autonomously navigating an underwater maze to retrieve a simulated submarine escape pod.

His responsibility had been designing the navigation system used to get to the pod, and he'd chosed to base the design on a species of pufferfish, _Torquigener tetraodontidae_, known for constructing [large circular geometric patterns][pufferfish] underwater in order to attract potential mates.
Neural simulations based on aquatic animals generally performed very well in this type of environment, and it stood to reason that this pufferfish might be especially suited due to it's apparent ability to process complicated geometric patterns.

[pufferfish]: https://doi.org/10.1038/srep02106

So far he'd been able to successfully abstract out the pufferfish's motor cortex and get it to control the AUV's thrusters, but no matter what he'd tried he hadn't been able to figure out it's visual cortex or sensory mechanisms.
He could potentially just simulate the pufferfish brain directly, but usually that took a lot of processing power, and he wasn't sure if the AUV's processor would be able to handle it.

At this point, he just had to hope the compiler would be able to optimize it enough to at least _work_, even if it couldn't run fast enough to be competitive.

Dejectedly, he set it running, and fell asleep in his chair.

--------

Matt awoke with a start to sunlight streaming in onto his face.
He checked the time - 12:30 - and started scrolled through his notifications before suddenly remembering he needed to be at the competition in 15 minutes.

He hastily grabbed the AUV and stuffed it in his bag with his laptop, only sparing a glance to ensure everything had compiled, before running as quickly as he could from the Computer Science Department to the Richards Building pool where the competition was being held.

"You got it figured out?" Jessica called to him as he arrived panting to the competition area.

"I ... I think so?" Matt gasped, trying to catch his breath.
The optimization report had said it had managed to fit the simulation onto the AUV's processor.
He pulled the AUV out of his bag and handed it to her.
"It will work, I'm pretty sure."

Jessica had been responsible for the mechanical design of the project, and she'd also been the one to who'd gotten him the neural scan he'd used as a basis for the programming.

"Mike messaged me and he should be here in - nnng there he is." she said, turning as she spotted Mike making his way through the light crowd.

Mike had done a lot of the electrical design, but more importantly he had also been the one who'd gotten most of their funding &mdash; apparently his uncle had made an absurd amount of money off the "bitcoin boom" in the thirties, and was only too glad to use some of it to help fund his nephew's education.

"Hey we ready?" he asked once he'd gotten to them.

Matt nodded. "Let's go."

--------

After attaching their 3D printed navigation target (a plastic tile in the shape of the ridges from a pufferfish circle) to the simulated pod and lowering it into the water, Matt hadn't been sure what he'd expected.

It turned out, their AUV performed very well.
Well enough to win the competition.
And in fact, well enough that they had initially been suspected of cheating by hardcoding the maze or controlling it remotely.
(This was resolved by running it through a new, randomly generated layout, and examining the hardware to make sure there wasn't a reciever that would allow remote control.)
The AUV just zipped through the maze, following pretty much the idea route first time, and their time to retrieve the capsule came in just under _a third_ that of the next fastest team.

This was despite the fact that they had accidentally _dropped_ the AUV beforehand, and while Matt had hoped nothing too serious had broken, the tinkle of glass from the camera had told him that was a lie.

His teammate's were overjoyed of course, and didn't really suspect anything, but Matt knew they hadn't just done well, they'd done _impossibly_ well.

--------

Matt got back to his apartment, set the AUV on his desk and powered it on, before unzipping his bag to pull out the 3D printed tile.
Immediately the AUV's thrusters spun up, and he zipped his bag shut to go shut it off, but as soon as he zipped it closed it shut off.
He opened the zipper a tiny bit.
Nothing.
Opened it a bit more, and immediately the thrusters spun up again until he zipped it back closed.

This was weird.

After disconnecting the thrusters (running them in air could potentially cause them to overheat) and wiring up a display, he pulled the tile back out.
As he had kind-of expected by this point, the display immediately reacted, and as he moved the tile around the display readout changed to match the direction to the tile.

He continued disconnecting various components, trying to isolate the cause.
He quickly eliminated the broken camera and the acoustic sensors, and after a few minutes all he had left was the bare processor board, attached to the power supply and the display.
Still the display consistently read out the direction to the tile.

This was _very_ weird.

--------

Matt knew he ought to be studying for his finals, but he didn't care.

He'd spent the rest of the weekend going through the software and hardware, eliminating pieces to try and figure out how it worked.
The pufferfish neural simulation appeared to be a necessary component, but he had eliminated nearly everything else that wasn't in some way required to run that simulation.
Frustratingly, all of his attempts to observe the simulation as it was running all caused it to stop working, but he was eventually able to pare the simulation to a single cluster of about 40 neurons that appeared to be responsible for this behavior.
None of them were related to any of the sensory corticies, and in fact most of them weren't even connected to each other.

So far he'd learned that the range of the effect was somewhat limited, as the further away the tile got, the weaker and less reliable the readings became.
By about 10 meters away, there would be about a 50/50 chance of a correct reading, and while this could be compensated for by taking several readings, there wasn't a lot that could be done to go much further than that.

By chance he'd also discovered that some types of plastics would block or hinder the effect.
He'd put the processor board in a plastic enclosure to protect it, and was at first confused when it had suddenly stopped working, then started again as soon as he re-opened the enclosure.
The AUV's hull hadn't caused issues though, and he tried several different enclosures to find one that worked.
So far he'd discovered that polyethylene and polystyrene  block it, but nylon and ABS have no effect.
And in testing this, he'd found that for plastics that do block the effect, the reading would actually deflect _around_ the sheet towards any openings over a particular size.

This at least explained how this effect had allowed the AUV to navigate the underwater maze so efficiently. 

Different materials appeared to impede the effect more than others, as well.
Lower grades of polyethylene were less effective at blocking it, and at a low enough grade it could penetrate if the material was thin enough.
He'd discovered this part placing the tile in a shopping bag, which had diminished (but not completely blocked) the signal.

--------

At this point, Matt still had no idea _how_ the device was able to detect the tile, but the fact of the matter is that it could, and it was able to do so much more efficiently than even the best current technologies.
He wasn't exactly sure what _he'd_ want to use it for, but if he figured out a way to overcome the range limitations this could have hundreds of potential uses, and even if not, it would still be quite valuable.
Especially given that it was so _cheap to make_ &mdash; his setup consisting of a hobbyist-grade neural processor and a cheap 3D printed part had only cost about $300!

He also knew that if he wanted to develop this properly, he needed money.
Not just to use for experimentation (although there were several things he wanted to try) but also to be able to patent the device to ensure he'd be able to profit off of it.

He'd met up with his team on the second floor of the student center.

"Whaddup, my bro from another hoe." Mike greeted him.

"Don't be vulgar, Mike." Jessica scolded him.

"So, I've done some more work with the navigation system I used for the competition, and I think we might actually have something worth developing further." Matt began.

"Yeah, that was awesome man, we totally wrecked everyone at the competition."

"What do you mean?" Jessica asked.

Matt pulled the processor board and the tile out of his bag.
He'd put together a quick visualization earlier, and turned his laptop to show them.
"I'm still not completely sure why it works, but the pufferfish neural simulation I based the navigation on is somehow still able to pick up the location of this tile, even without any obvious sensing mechanism."

He handed the tile to them, as the 3D model on screen moved in tandem with it.

Mike picked it up. "That's pretty neat."

Jessica was a bit more skeptical. "So like what, magic?"

"I honestly don't know, although there's a few possibilities I haven't ruled out completely.
But whatever it's doing, it's able to locate the tile on par with most room-scale VR setups, using less than a percent of the compute power those systems need, and with hardware costing only a tenth as much."

Mike slapped his hand onto the table. "I'm in."

"What?" Matt was put off-base.

"You're gonna drop out and start a company and develop this stuff. I said I'm in."

"I'm not dropping out!
I don't even have that kind of money, and there's a million and one other things beside!"

"Don't worry about it, my uncle'll give us a loan. He's been well, not exactly pressuring me, but he'd love this sort of thing. You in Jess?"

"I'm definitely interested if this pans out, but we can't just abandon schooling."

"_Jess_, you're either in or out. Are you in, or out?"

 "It's not that I don't trust you guys, but that's a rather extraordinary claim, and I'm going to want more evidence than just a cheap demo that could be working any number of ways."

"_Jess_, _in_, or _out_."
She groaned. "Fine.
But you'd better be able to provide more solid evidence that this all actually works the way you're claiming."

--------

[Next][next]

[next]: //coming-soon
