# Project 4: Cloth Sim

## Part 1: 
**Take some screenshots of scene/pinned2.json from a viewing angle where you can clearly see the cloth wireframe to show the structure of your point masses and springs.**

Overall picture:
![Overall scene/pinned2.json picture](/img-4/1-full.png)

Zoomed in picture:
![Zoomed in picture of scene/pinned2.json](/img-4/1-close.png)

**Show us what the wireframe looks like (1) without any shearing constraints, (2) with only shearing constraints, and (3) with all constraints.**

* 	(1) Without any shearing
![Without any shearing](/img-4/1-no-shear.png)
*	(2) With only shearing constraints
![Only shearing constraint](/img-4/1-only-shear.png)
*	(3) With all constraints:
![With all constraints (structural, shearing, and bending))](/img-4/1-full.png)



# Part 2:
**Experiment with some the parameters in the simulation. To do so, pause the simulation at the start with `P`, modify the values of interest, and then resume by pressing `P` again. You can also restart the simulation at any time from the cloth's starting position by pressing `R`.**
* 	**Describe the effects of changing the spring constant ks; how does the cloth behave from start to rest with a very low ks? A high ks?**

The provided normal cloth has: `ks = 5000 N/m`, `density = 15 g/cm^2`, `damping = 0.200000%`

![Normal cloth](/img-4/normal-ks-5000.png)

Now, changing the parameters to see the individual effect of each on the cloth:

1. Low `ks = 10 N/m` has more sketchy cloth.
![Low ks = 10](/img-4/low-ks-10.png)

2. High `ks = 100000 N/m` has less sketchy, in other words, stiffer cloth.
![High ks = 100000](/img-4/high-ks-100000.png)

3. Low `density = 5 g/cm^2` makes the cloth droops down less.
![Low density cloth](/img-4/low-density.png)

4. High `density = 50 g/cm^2` makes the cloth droops down more.
![High density cloth](/img-4/high-density.png)

5. Low `damping = 1.000000 %` makes the cloth swap less.
![Low damping cloth](/img-4/low-damping.png)

6. High `damping = 0.000000 %` makes the cloth swap MUCH more (like there is a storm or something high wind).
![High damping cloth](/img-4/high-damping.png)

*   **Show us a screenshot of your shaded cloth from scene/pinned4.json in its final resting state! If you choose to use different parameters than the default ones, please list them.**

Wire-framed pinned4.json:

![Wireframed pinned4.json](/img-4/pinned4-wire.png)

Normal shaded pinned4.json:

![Shaded pinned4.json](/img-4/pinned4-normal.png)


