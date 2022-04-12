# Project 4: Cloth Sim

## Part 1: Masses and springs
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



# Part 2: Simulation via numerical integration
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



## Part 3: Handling collisions with other objects
**Show us screenshots of your shaded cloth from scene/sphere.json in its final resting state on the sphere using the default `ks = 5000` as well as with `ks = 500` and `ks = 50000`. Describe the differences in the results.**

Default `ks = 5000` at final resting state (this is the basic "drapness" I will be comparing with other ks values):
![Cloth drape over sphere, ks = 5000](/img-4/sphere-normal.png)


Cloth draped on sphere with `ks = 500` has much more parts of the cloth that **tightly hug** the sphere than that of the `ks = 5000`.
![Cloth drape over sphere, ks = 500](/img-4/sphere-ks-low.png)

Cloth draped on sphere with `ks = 50000` has much more parts of the cloth that **stiff out**/does not bend with the sphere than that of the `ks = 5000`.
![Cloth drape over sphere, ks = 500](/img-4/sphere-ks-high.png)

**Show us a screenshot of your shaded cloth lying peacefully at rest on the plane.**

My basic cloth lying peacefully on the ground plane:
![Cloth lying on plane - colored](/img-4/plane-color.png)

If viewing the above picture isn't easy enough to determine if it's right on the plane or not, this is the wire-framed image:
![Cloth lying on plane - wireframe](/img-4/plane-wireframe.png)


## Part 4: Handling self-collisions

**Show us at least 3 screenshots that document how your cloth falls and folds on itself, starting with an early, initial self-collision and ending with the cloth at a more restful state (even if it is still slightly bouncy on the ground).**

Before cloth falls:
![Before fall](/img-4/self-fold-1.png)

Starting to fall. Cloth folds onto itself more at the bottom:
![Alittle self-fold at the bottom](/img-4/self-fold-2.png)

Folds more onto itself and spread a bit on the ground as more cloth falls:
![More self-fold and spread out onto the ground](/img-4/self-fold-3.png)

Entire cloth fall on the ground. You can see that the wavy self-fold at the edge of the cloth:
![Before fall](/img-4/self-fold-4.png)

At resting state, the previous cloth slowly spread out more to cover the ground due to gravity: (rest state is still a bit wavy, but it is spread out more than with low density)
![Before fall](/img-4/self-fold-5.png)


At resting state. The other side of the cloth. Also see the self-fold.
![Before fall](/img-4/self-fold-6.png)


**Vary the density as well as ks and describe with words and screenshots how they affect the behavior of the cloth as it falls on itself.**

Low `density = 5`. The cloth is more folded onto itself and spreads out on the ground less:
![Low density=5 self-fold](/img-4/self-fold-low-density.png)

High `density = 500`. The cloth is less folded onto itself and spreads out on the ground more, as gravity pulls it down more due to its high density:
![High density=500 self-fold](/img-4/self-fold-high-density.png)

Low `ks = 500`. The cloth has more rumpy, scuffle parts. It folds and creases over itself more.
![Low ks=500 self-fold](/img-4/self-fold-low-ks.png)

High `ks = 50000`. The cloth is MUCH smoother (like silk). It spreads out more and has less mini-folds/rumpy parts on the material.
![High ks=500000 self-fold](/img-4/self-fold-high-ks.png)
