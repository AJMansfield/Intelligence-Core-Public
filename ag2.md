[First][first] | Next

> Therefore shall a man leave his father and his mother.
> 
> _&mdash; Genesis 2:24_

--------

Angela had left her birth colony just over a year ago to go on her diasperation.
As part of a Phascolian's transition to adulthood, they would travel long distances from their birth colony to meet up with a group of other Phascolians on their diasperations, and form a new colony with them where they met.
While it wasn't unheard of or looked down on for pairs of colony-brothers or colony-sisters of a similar age to travel together on their diasperations, most, like Angela, traveled alone, trusting their instincts to lead them to the right place at the right time.

Because they always would.
It was nigh unheard of, short of injury or death, for a Phascolian following their instincts to not eventually make it to a colony.
Even across relativistic distances, dozens of Phascolians from completely different star systems had been known to arrive within days of each other, without any sort of prior coordination.
There were scientific theories as to how exactly this happened, but for now that didn't matter to her.

Angela's instincts had led her to leave her birth planet and travel 18 light years to the planet she would later call home, and that the Humans called Earth.
While for her it had only been a year (she'd spent most of that time in artificial hibernation), this meant that there was no going back &mdash; for everyone on her birth planet, and the galaxy at large, she'd already been gone for nearly 20 years.

After de-orbiting, she had touched down in her reentry pod a few kilometers north of a Human settlement called Elko, Nevada.
She had initially been worried that the Humans might be arsenoids, because of the high arsenic levels she'd found near her landing site.
Fortunately for her, they turned out to not only be phosphenoids like her, but they also used the same basic cellular metabolism and most of the same amino acids as her.
This meant she might even be able to digest most of the same foods, and while she'd still have to take norvaline supplements, that was vastly preferable to eating packed rations until her colony could plant and grow their first crop.

--------

After several more chance discoveries, Matt had found a way to overcome the range limitations of their new technology.

He'd originally tried seeing if slight modifications to the 3D-printed tile or neural simulation might give better results.
While he was able to improve it slightly (the -3dB point was now 11 meters away rather than 10), the process of 3D printing each individual tile took several hours, meaning it could take years to properly optimize the design.

The breakthrough came when he was reading over the [original paper][pufferfish] that had started it all on his e-reader, when Jessica ran in.

"The detector just started acting up for some reason; it's pointing completely the wrong way now."

Matt closed the e-reader. "Let's see."

The device had appeared to be working when he'd gotten back to the lab, but he decided to re-locate to the lab in case it acted up again.

He re-opened the e-reader and read for a bit, then scrolled back up to the paper's photographs.

"There it is, it's acting weird again."

He closed the e-reader and walked over to see what Jessica was talking about.

"It just stopped again."

He set the e-reader next to the processor and opened it.
Immediately the detector's reading jumped to point at it.

No way.

"Wait. This means ... " Matt began and trailed off.

"We don't need to 3D-print everything." Jessica finished for him.

And then it hit him.
"In fact, better than that, we can hook this up to the computer in a feedback loop to let the computer optimize the pattern _directly_.
What's this thing's refresh rate, like 15 frames per second?"

"In fact, can we use just _any_ substrate?"
He sent the photo to their printer and closed the e-reader.
As soon as the printer had finished depositing the last bit of ink needed for the pattern, the indicator jumped to point at the printout.

--------

Phascolians were naturally primed to be able to quickly pick up new languages during their diasperations, as often most of the members of a new colony wouldn't even speak the same language when they arrived.
New colonies on previously-unsettled planets would usually develop a hodge-podge language of its own built out of pieces of each of its member's birth tongues.
But in cases where a colony settled near an existing population, such as Angela would be doing here on Earth, it was more common for a colony to end up using the existing local language than their own.

Angela had chosen her name mostly because it sounded somewhat similar to her birth name, but the pun of "anglicizing" her name in this way wasn't lost on her either.
She'd also chosen the name "Phascolian" to describe her species, in reference to their marsupial biology, but she didn't really like the name &mdash; it was too harsh sounding, and didn't feel right.

It hadn't been too difficult to live among the Humans in Elko while she waited for the others of her kind to arrive.
She was 138 centimeters tall, making her a good deal shorter than most Humans, but they shared the same basic kinematics and locomotion, as well most of the same basic facial structure.
The only major difference visible at a glance were her articulated ears located at the top of her head like a cat's, rather than on the sides like a Human.
While she did sometimes get weird looks, at least she was above "it's not polite to stare" territory by human standard, and that was fine by her.

--------

Matt and Jessica had been discussing different options for how to allow the computer to automatically adjust the distance from the detector to the e-reader automatically measure the strength.
Jessica had wanted to build a setup with some sort of moveable carriage, but even a short length of track could get really expensive, and theoretically they might end up needing hundreds of meters.
Matt had come up with the idea to set up a bunch of detectors and displays in an arrangement similar to a [Golomb ruler][golomb], but that added significant complexity to the setup, and they'd need a lot of e-readers and detectors to do it.

But it was actually Mike that had the critical insight for how to do it.
"Dude, just stick some plastic in the way."

Matt had already discovered weeks ago that some kinds of plastic could impede the effect, but it hadn't ever occurred to him to use this to simulate distance.
After a bit of experimentation, they put together a plastic box with a servo that could partially cover a hole drilled in the box.
And then they set the computer controlling the apparatus to start optimizing the pattern.

--------

After about half a year living in Elko, Angela had started to feel like she needed to move on.
She was still on her diasperation, and hadn't yet actually met up with her colony yet.
It was odd that she hadn't spotted any other Phascolian ships coming down, but perhaps they had arrived before her.
In any case, she needed to move on, and her instincts told her to go East.

--------

Overnight, the algorithm had made steady improvements to the range, before suddenly becoming extremely erratic.
At first it had apparently just shrunk the image down with very little modification, until running into the limits of the display's resolution.
Once it was there, there was little it could do but randomly change pixels until it was all a garbled mess.

This was not what Matt had expected at all, but in some ways this was actually good news:
If just making the pattern smaller made it more powerful, then later miniaturization of the tech would be a breeze.
The algorithm hadn't gained a lot from its efforts though.
The best instance had had a range of just under 17 meters &mdash; still a new record, but hardly earth-shattering.

It took Matt several hours to work out a way to fix this issue.
Simply normalizing the images by resizing them all to the same size didn't work &mdash; the algorithm quickly figured out that it could add 'decoy' pixels to defeat the normalization.
But he was able to figure out a way to simulate the aliasing at a larger scale, and penalized patterns that performed worse when aliased, and was successfully able to discourage the system from shrinking the pattern too far.

With this change the optimization process took much longer, but after a week there were significant improvements.
One of the first major changes that improved performance was when the algorithm converted everything to black-and-white, and sharpened all of the edges to clean lines.
With this change, it was now able to detect the pattern out to a simulated 80 meter distance.
At this point, they'd had to replace the original box with one with a much smaller opening, and Matt changed the algorithm to use the SVG vector format rather than a PNG.

A week after that, they ran into another issue, as the hole for the tablet's charging cable was big enough to cause issues with the shielding.
At this point a high-resolution printout of the pattern, scaled down as far as they could without aliasing, could be detected over 3 km away.
The algorithm had started adding additional outer rings to the pattern, and at this point had nearly reached the edge of the e-reader's screen, so they also needed to get a higher-resolution screen to be able to display it.

--------

Angela had initially been amazed by the Human's technology.

On her birth world, automation of any kind was a luxury, and required massive tomes filled with sigils to power anything more complex than a simple on-off switch.
Especially in the case of Human's portable devices, she doubted it was even physically possible to fit the mind-bogglingly complex sets of sigils that would be needed for even basic functionality, and locating them elsewhere had its own challenges.

The humans did have libraries (although they were much less common than on her birth world), but none of the books she found contained a single sigil.
Even those that weren't prominently labeled as outright fabrications consisted of just comments!
To be fair, once she'd learned the language, she found they were some of the best-written documentation she had ever read, going into incredible depth on the specifics of different natural phenomena, but still!

She had even tried disassembling one of the Human laptops, but she hadn't been able to make sense of any of it at all, and she had simply given up understanding how Human technology worked.
The squiggles connecting the innumerable black rectangles inside were nothing like the sigils she had learned in her training, and it hadn't worked at all after she'd tried putting it back together.

Now though, she just took Human tech for granted, and summoned an Uber with her smartphone.
She wasn't sure how far she needed to go, so she had just selected Denver, Colorado.
That felt like it should be far enough.

--------

They'd applied for and gotten a patent on the technology, but at this point they were still too busy improving it to really consider applications yet.
Mike had tried to see if anyone else wanted to license the technology, but the few companies he were even able to get in contact with had been extremely skeptical of it, and nothing had turned up in that area yet.
Fortunately, once they'd shown Mike's uncle the new version of their prototype, he'd offered them a staggering amount of money in exchange for just a 5% share of the company.

They'd used a part of this to lease a space in an industrial park in Salt Lake City, in order to set up a 'proper lab' for this stuff, and had it fitted with a layer of HDPE isolation material to screen out interference.

Beyond simply increasing the range, they'd also made several other important discoveries.
The pattern didn't necessarily have to be visible &mdash; even if you covered a printout with (non-latex) paint it could still be detected just as strongly, as long as the paint was dissimilar enough to the ink used to print it.
It also worked with a very wide range of substrates, although more chemically pure materials seemed to perform better.

After a month, the optimization algorithm had filled the entire 110-inch screen they'd gotten for it.
At this point they could no longer directly measure the range, but based on their calculations from the test results, it should be detectable from at least 100,000 km away.

So they sent the design to an integrated circuit fab, and had a million copies made, each at only half a millimeter across.

--------

It turned out Angela hadn't needed to go all the way to Denver, or even most of the way.
As soon as she'd crossed into the Salt Lake valley, she knew: this is the place.

[First][first] | Next


[pufferfish]: //doi.org/10.1038/srep02106
[golomb]: //en.wikipedia.org/wiki/Golomb_ruler
[first]: ag1.md
