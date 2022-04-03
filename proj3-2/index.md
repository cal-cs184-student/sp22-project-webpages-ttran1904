# Project 3-2

## Part 1: Mirror and Glass Materials
**Show a sequence of six images of scene `CBspheres.dae` rendered with `max_ray_depth` set to 0, 1, 2, 3, 4, 5, and 100.**
![Spheres - max ray depth 0](/img-3.2/spheres_0.png)
Ray depth 0
![Spheres - max ray depth 1](/img-3.2/spheres_1.png)
Ray depth 1
![Spheres - max ray depth 2](/img-3.2/spheres_2.png)
Ray depth 2
![Spheres - max ray depth 3](/img-3.2/spheres_3.png)
Ray depth 3
![Spheres - max ray depth 4](/img-3.2/spheres_4.png)
Ray depth 4
![Spheres - max ray depth 5](/img-3.2/spheres_5.png)
Ray depth 5
![Spheres - max ray depth 100](/img-3.2/spheres_100.png)
Ray depth 100

**Point out the new multibounce effects that appear in each image** 

also explains the question:

**Explain how these bounce numbers relate to the particular effects that appear.**

Images above are ordered based on maximum ray depth: (64 samples per pixel and 4 samples per light)
*   `0`: No object has received light on its surface. Therefore, pitch black except for the light source.
*   `1`: Only has 1 bounce (i.e. direct illumination). On the mirror/glass spheres, I can only see image of the light source, because it is the only thing that has a direct 1 bounce (so the walls are not included.) Also, the ceiling wall is black (except for the white light source) because it hasn't receive 2 bounce from other objects below it.
*   `2`: Now I can see diffusive objects on the mirror/glass spheres. Closely observe the left sphere, it has the reflection of the right sphere, but it's black! That's because image of the right sphere only contain up to 2 bounces (light -> right sphere -> left sphere) and has no more room for other diffusive objects that has `> 2` bounces. On the other hand, we can see that the left sphere (as appear on the right sphere) is a bit fuzzy/noisy. This is because rays from diffusive objects -> right sphere -> left sphere makes it noiser.
*   `3`: Both the left and right spheres have a more accurate reflection represetation of the other spheres (less noisy, much clearer, etc.) In the shadow of the right sphere, we can see the bright reflexive spot refracted from the right source through the right sphere to arrive on the ground. We can also see the red and blue walls mixing with other white walls in this new image.
*   `4, 5, 100`: starting to have almost identical results after 4 maximum ray depth. Right sphere was optimal at 3 bounces max and now it has become slightly noisier. Progressively through the images, the refracted spot under the right sphere gets a tiny bit stronger. In addition, there is a bright shadow on the rightsphere surface, where it is close to the refracted spot. This is probability due to more max ray allowed increase the brightness of the sphere surface where will refract before hitting the ground.


## Part 3
**In a few sentences, explain the ideas behind environment lighting (i.e. why we do it/how it works).**
Environment lighting represents source that is "infinitely" far away, such as in the real-world where we have light source that are much further from the object then the light source in the enclosed room/box that we see in the previous part. How it works is that the light from each direction is defined by a texture map parameterized by phi and theta.

![Environment Light](/img-3.2/envirolight.png)
Environment light example figure from the project spec

I am using the Field background, shown below:

![Grace Background](/img-3.2/field.png)

**Show the `probability_debug.png` file for the .exr file you are using, generated using the save_probability_debug() helper function after initializing your probability distributions.**

![probability_debug.png file](/img-3.2/probability_debug.png)



**Use the `bunny_unlit.dae` scene and your environment map `.exr` file and render two pictures, one with uniform sampling and one with importance sampling. Use 4 samples per pixel and 64 samples per light in each. Compare noise levels.**

With Uniform sampling (from staff/provided skeleton code)

![bunny_unlit - Uniform Sampling](/img-3.2/bunny_unlit_hemisphere.png)

With Importance sampling:

![bunny_unlit - Importance sampling](/img-3.2/bunny_unlit_importance.png)

Importance sampling has a clearer image. It has more noise or freckles on the bunny, as seen obviously on the lighter areas of the uniform sampling image.


**Use a different image (if you did part 2, we recommend `bunny_microfacet_cu_unlit.dae`) and your environment map `.exr` file and render two pictures, one with uniform sampling and one with importance sampling. Use 4 samples per pixel and 64 samples per light in each. Compare noise levels.**

I did Part 2 (but only want to get graded on Part 1. The code works), so I will use the recommended file `bunny_microfacet_cu_unlit.dae`.

Using `-l 256 -s 4 -t 8 -m 7`:
*   With Uniform Sampling:

![cu_bunny with uniform sampling](/img-3.2/cu_bunny_uniform.png)

*   With Importance Sampling:

![cu_bunny with importance sampling](/img-3.2/cu_bunny_importance.png)

The importance sampling is less noisy. It has clearer image of the lobe of the right ear, tail, and front paw of the bunny.



<!-- ## Part 2
**Show a sequence of 4 images of scene CBdragon_microfacet_au.dae rendered with `α` set to 0.005, 0.05, 0.25 and 0.5. Describe the differences between different images.** -->