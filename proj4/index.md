# Project 4: Cloth Sim


## Part 1: Masses and springs
**Take some screenshots of scene/pinned2.json from a viewing angle where you can clearly see the cloth wireframe to show the structure of your point masses and springs.**

Overall picture:
<!-- ![Overall scene/pinned2.json picture](../img-4/1-full.png) -->

<img src="../img-4/1-full.png" width="200" height="200">

Zoomed in picture:
<!-- ![Zoomed in picture of scene/pinned2.json](../img-4/1-close.png) -->
<img src="../img-4/1-close.png" width="200" height="200">

**Show us what the wireframe looks like (1) without any shearing constraints, (2) with only shearing constraints, and (3) with all constraints.**

* 	(1) Without any shearing
<!-- ![Without any shearing](../img-4/1-no-shear.png) -->
<img src="../img-4/1-no-shear.png" width="200" height="200">

*	(2) With only shearing constraints
<!-- ![Only shearing constraint](../img-4/1-only-shear.png) -->
<img src="../img-4/1-only-shear.png" width="200" height="200">

*	(3) With all constraints:
<!-- ![With all constraints (structural, shearing, and bending))](../img-4/1-full.png) -->
<img src="../img-4/1-full.png" width="200" height="200">



# Part 2: Simulation via numerical integration
**Experiment with some the parameters in the simulation. To do so, pause the simulation at the start with `P`, modify the values of interest, and then resume by pressing `P` again. You can also restart the simulation at any time from the cloth's starting position by pressing `R`.**
* 	**Describe the effects of changing the spring constant ks; how does the cloth behave from start to rest with a very low ks? A high ks?**

The provided normal cloth has: `ks = 5000 N/m`, `density = 15 g/cm^2`, `damping = 0.200000%`

<!-- ![Normal cloth](../img-4/normal-ks-5000.png) -->
<img src="../img-4/normal-ks-5000.png" width="200" height="200">

Now, changing the parameters to see the individual effect of each on the cloth:

1. Low `ks = 10 N/m` has more sketchy cloth.
<!-- ![Low ks = 10](../img-4/low-ks-10.png) -->
<img src="../img-4/low-ks-10.png" width="200" height="200">


2. High `ks = 100000 N/m` has less sketchy, in other words, stiffer cloth.
<!-- ![High ks = 100000](../img-4/high-ks-100000.png) -->
<img src="../img-4/high-ks-100000.png" width="200" height="200">

3. Low `density = 5 g/cm^2` makes the cloth droops down less.
<!-- ![Low density cloth](../img-4/low-density.png) -->
<img src="../img-4/low-density.png" width="200" height="200">

4. High `density = 50 g/cm^2` makes the cloth droops down more.
<!-- ![High density cloth](../img-4/high-density.png) -->
<img src="../img-4/high-density.png" width="200" height="200">

5. Low `damping = 1.000000 %` makes the cloth swap less.
<!-- ![Low damping cloth](../img-4/low-damping.png) -->
<img src="../img-4/low-damping.png" width="200" height="200">

6. High `damping = 0.000000 %` makes the cloth swap MUCH more (like there is a storm or something high wind).
<!-- ![High damping cloth](../img-4/high-damping.png) -->
<img src="../img-4/high-damping.png" width="200" height="200">

*   **Show us a screenshot of your shaded cloth from scene/pinned4.json in its final resting state! If you choose to use different parameters than the default ones, please list them.**

Wire-framed pinned4.json:

<!-- ![Wireframed pinned4.json](../img-4/pinned4-wire.png) -->
<img src="../img-4/pinned4-wire.png" width="200" height="200">


Normal shaded pinned4.json:

<!-- ![Shaded pinned4.json](../img-4/pinned4-normal.png) -->
<img src="../img-4/pinned4-normal.png" width="200" height="200">


## Part 3: Handling collisions with other objects
**Show us screenshots of your shaded cloth from scene/sphere.json in its final resting state on the sphere using the default `ks = 5000` as well as with `ks = 500` and `ks = 50000`. Describe the differences in the results.**

Default `ks = 5000` at final resting state (this is the basic "drapness" I will be comparing with other ks values):
<!-- ![Cloth drape over sphere, ks = 5000](../img-4/sphere-normal.png) -->
<img src="../img-4/sphere-normal.png" width="200" height="200">

Cloth draped on sphere with `ks = 500` has much more parts of the cloth that **tightly hug** the sphere than that of the `ks = 5000`.
<!-- ![Cloth drape over sphere, ks = 500](../img-4/sphere-ks-low.png) -->
<img src="../img-4/sphere-ks-low.png" width="200" height="200">


Cloth draped on sphere with `ks = 50000` has much more parts of the cloth that **stiff out**/does not bend with the sphere than that of the `ks = 5000`.
<!-- ![Cloth drape over sphere, ks = 500](../img-4/sphere-ks-high.png) -->
<img src="../img-4/sphere-ks-high.png" width="200" height="200">

**Show us a screenshot of your shaded cloth lying peacefully at rest on the plane.**

My basic cloth lying peacefully on the ground plane:
<!-- ![Cloth lying on plane - colored](../img-4/plane-color.png) -->
<img src="../img-4/plane-color.png" width="200" height="200">

If viewing the above picture isn't easy enough to determine if it's right on the plane or not, this is the wire-framed image:
<!-- ![Cloth lying on plane - wireframe](../img-4/plane-wireframe.png) -->
<img src="../img-4/plane-wireframe.png" width="200" height="200">

## Part 4: Handling self-collisions

**Show us at least 3 screenshots that document how your cloth falls and folds on itself, starting with an early, initial self-collision and ending with the cloth at a more restful state (even if it is still slightly bouncy on the ground).**

Before cloth falls:
<!-- ![Before fall](../img-4/self-fold-1.png) -->
<img src="../img-4/self-fold-1.png" width="200" height="200">


Starting to fall. Cloth folds onto itself more at the bottom:
<!-- ![Alittle self-fold at the bottom](../img-4/self-fold-2.png) -->
<img src="../img-4/self-fold-2.png" width="200" height="200">

Folds more onto itself and spread a bit on the ground as more cloth falls:
<!-- ![More self-fold and spread out onto the ground](../img-4/self-fold-3.png) -->
<img src="../img-4/self-fold-3.png" width="200" height="200">

Entire cloth fall on the ground. You can see that the wavy self-fold at the edge of the cloth:
<!-- ![Before fall](../img-4/self-fold-4.png) -->
<img src="../img-4/self-fold-4.png" width="200" height="200">

At resting state, the previous cloth slowly spread out more to cover the ground due to gravity: (rest state is still a bit wavy, but it is spread out more than with low density)
<!-- ![Before fall](../img-4/self-fold-5.png) -->
<img src="../img-4/self-fold-5.png" width="200" height="200">


At resting state. The other side of the cloth. Also see the self-fold.
<!-- ![Before fall](../img-4/self-fold-6.png) -->
<img src="../img-4/self-fold-6.png" width="200" height="200">


**Vary the density as well as ks and describe with words and screenshots how they affect the behavior of the cloth as it falls on itself.**

Low `density = 5`. The cloth is more folded onto itself and spreads out on the ground less:
<!-- ![Low density=5 self-fold](../img-4/self-fold-low-density.png) -->
<img src="../img-4/self-fold-low-density.png" width="200" height="200">

High `density = 500`. The cloth is less folded onto itself and spreads out on the ground more, as gravity pulls it down more due to its high density:
<!-- ![High density=500 self-fold](../img-4/self-fold-high-density.png) -->
<img src="../img-4/self-fold-high-density.png" width="200" height="200">

Low `ks = 500`. The cloth has more rumpy, scuffle parts. It folds and creases over itself more.
<!-- ![Low ks=500 self-fold](../img-4/self-fold-low-ks.png) -->
<img src="../img-4/self-fold-low-ks.png" width="200" height="200">

High `ks = 50000`. The cloth is MUCH smoother (like silk). It spreads out more and has less mini-folds/rumpy parts on the material.
<!-- ![High ks=500000 self-fold](../img-4/self-fold-high-ks.png) -->
<img src="../img-4/self-fold-high-ks.png" width="200" height="200">



# Part 5: Shader
**Explain in your own words what is a shader program and how vertex and fragment shaders work together to create lighting and material effects.**
*   Shaders are separate programs running in parallel ini GPU. It executes sections of the graphics pipeline: takes in an input and outputs a 4 dimensional vector.
*   Vertex shader apply transforms to vertices, modifying their geometric properties (positions, normal vectors, etc.). The vertex shader's output is the input to fragment shader. (`gl_Position`)
*   Fragment shader takes in geometric properties of each fragments and output colors for that fragment `out_color`.


**Explain the Blinn-Phong shading model in your own words. Show a screenshot of your Blinn-Phong shader outputting only the ambient component, a screen shot only outputting the diffuse component, a screen shot only outputting the specular component, and one using the entire Blinn-Phong model.**

Only ambient component:
<!-- ![Sphere covered with cloth ambient](../img-4/phong-ambient.png) -->
<img src="../img-4/phong-ambient.png" width="200" height="200">

Only diffuse component:
<!-- ![Sphere covered with cloth diffuse](../img-4/phong-diffuse.png) -->
<img src="../img-4/phong-diffuse.png" width="200" height="200">

Only specular component:
<!-- ![Sphere covered with cloth specular](../img-4/phong-specular.png) -->
<img src="../img-4/phong-specular.png" width="200" height="200">


All 3 components: ambient, diffuse, and specular
<!-- ![Sphere covered with cloth with all 3 componenets](../img-4/phong-all.png) -->
<img src="../img-4/phong-all.png" width="200" height="200">


**Show a screenshot of your texture mapping shader using your own custom texture by modifying the textures in /textures/**

Using this random texture pic I got on Google:
<!-- ![Dessert ground cracks texture pic](../img-4/texture-pic.png) -->
<img src="../img-4/texture-pic.png" width="200" height="200">


I get this cloth and sphere image:
<!-- ![Cloth and sphere with texture mapping](../img-4/texture.png) -->
<img src="../img-4/texture.png" width="200" height="200">


**Show a screenshot of bump mapping on the cloth and on the sphere. Show a screenshot of displacement mapping on the sphere. Use the same texture for both renders. You can either provide your own texture or use one of the ones in the textures directory, BUT choose one that's not the default texture_2.png. Compare the two approaches and resulting renders in your own words. Compare how your the two shaders react to the sphere by changing the sphere mesh's coarseness by using -o 16 -a 16 and then -o 128 -a 128.**

The following methods use `-o 128 -a 128` and the dessert ground crack texture map that I used before:

Bump mapping cloth:
<!-- ![Bump cloth](../img-4/bump-cloth.png) -->
<img src="../img-4/bump-cloth.png" width="200" height="200">

Bump mapping sphere:
<!-- ![Bump sphere](../img-4/bump-sphere.png) -->
<img src="../img-4/bump-cloth.png" width="200" height="200">

Bump mapping cloth over sphere:
<!-- ![Bump cloth over sphere](../img-4/bump-clothsphere.png) -->
<img src="../img-4/bump-clothsphere.png" width="200" height="200">

**Show a screenshot of your mirror shader on the cloth and on the sphere.
Explain what you did in your custom shader, if you made one.**

Mirror shaded over just cloth:
<!-- ![Cloth mirror shaded](../img-4/mirror-cloth.png) -->
<img src="../img-4/mirror-cloth.png" width="200" height="200">

Mirror shaded over just sphere:
<!-- ![Sphere mirror shaded](../img-4/mirror-sphere.png) -->
<img src="../img-4/mirror-sphere.png" width="200" height="200">

Mirror shaded over clother draped over sphere:
<!-- ![Cloth and sphere mirror shaded](../img-4/mirror-clothsphere.png) -->
<img src="../img-4/mirror-clothsphere.png" width="200" height="200">
