# Project 1

## Task 1
In order to rasterize a triangle I did these steps:
* Make the order of the points are clockwise: helpful to keep track that for every
line test, we rasterize the **inside** the triangle will be on the right of the test line. To do make point `p0, p1, p2` clockwise, I compare the slope:
    * `a = (y1 - y0)/(x1 - x0) `
    * `b = (y2 - y1)/(x2 - x1)`

    If:
    * `a > b`: clockwise
    * `a < b`: counter clockwise
    * `a = b`: colinear
* Bound a pixel box to rasterize the image. Minimum and maximum x & y bounds.
* Do 3 line tests: I created a helper function call `line_test` that takes in point `p` and compare to the line with 2 reference points `rf1` and `rf2`.
* If all 3 line test succeed. I will rasterize that point

My algorithm is no worse than one that checks each sample within the bounding box of the triangle.
That is because for each point, if it fails 1 line test, then the program will ignore that
point and continue to test the next point. Therefore, it will save a lot of time instead of 
checking all 3 points at once.

![SVG6](/img/task1-svg4.png?raw=true)

I optimized it with bounding box for each triangle. The time (clock() unit time miliseconds):
* No bounding box: 1997983
* Has bounding box: 9222



## Task 2
Supersampling nxn of a pixel is, instead of sampling just 1 center point,
I would have to divide that pixel into nxn squares and sample the centers of those points. Supersampling is useful because sampling could be better in higher resolution, and thus reduce alias like jaggies in ordinary sampling.

My super sampling algorithm separate the **actual matrix** (`rgb_framebuffer_target`) and the super **super sampling matrix** (`sample_buffer`). The reason why I need a super sampling matrix is to store the result of splitting and sampling data points from nxn sub-pixels with every pixel. Thus, I created 2 different functions `fill_pixel` and `fill_pixel` to respectively fill the pixel in the actual matrix and the super sampling matrix.

Now, in the `rasterize_triangle` function, I modified my algorithm to go over every sub-pixel within 1 pixel and fill out the super sampling matrix.

Other utilities functions accordingly modified:
* `set_sample_rate`: set rate
* `set_framebuffer_target`: separate the smaller real matrix and the larger super sampling matrix
* `resolve_to_framebuffer`: after rasterizing all the shapes in the super sampling matrix, this function converts that matrix into the real matrix, which will be used later to rasterize the lower resolution points. It basically adds up all the nxn sub-pixels' colors and divide it by the sample rate, which gives the average.
* `clear_buffers()`: no change. Sufficient
* `fill_pixel()`: no change.

For `basic/test4.svg`, the images are:

![SVG6](/img/task2-svg4-01.png?raw=true)
![SVG6](/img/task2-svg4-04.png?raw=true)
![SVG6](/img/task2-svg4-16.png?raw=true)

Based on the pixel inspector, sample rate 1 just gives a 0 or 1 value of the pink pixel if the center is within that skinny triangle. However, increasing sample rate to 4 will divide the pixel into 4 smaller sub-pixels that can average out the more accurate likelihood values of the pixels. Further increasing to 16 will make the picture more accurate and less white pixels that are not supposed to cut that continuous triangle.


## Task 3
I modified my cubeman so that he is raising his whole left arm up (waving) and bending his right elbow slightly. It looks like he is trying to say hello.


![robot](/img/my_robot.png?raw=true)


## Task 4
Barycentric coordinates is an alternative way to describe the points in a shape (in this case, a triangle). The basics of barycentric cordinates is to represent a point with 3 distances, each from the 3 vertices.

Let `α, β, γ` be distances from vertex A, B, and C of the triangle, such that `α + β + γ = 1`. A point `V` inside the triangle is defined as `V = αV_A + βV_B + γV_C`.

![barycentric](/img/barycentric.png?raw=true)

The color wheel:

![colorwheel](/img/colorwheel.png?raw=true)


## Task 5
Pixel sampling is using a barycentric coordinate to sample a point's color in every triangle of an image.

One way to implement this is to use **nearest sampling**, choosing 1 texture coordinate closest to that point (barycentric-wise). Another way to implement is to use **bilinear filtering**, choosing 4 closest barycentric points and linearly interpolating them to get the final value. The second method will give a smoother texture in the final image, because it relies on multiple points to basically "average"/interpolate out.

With nearest sampling:
![nearest sampling- sr 1](/img/n-1.png?raw=true)
![nearest sampling- sr 16](/img/n-16.png?raw=true)

With bilinear sampling
![bilinear sampling- sr 1](/img/bi-1.png?raw=true)
![bilinear sampling- sr 16](/img/bi-16.png?raw=true)

For nearest samples generally have more aliasing error for lower sampling rate, such as 1. This is because when the coordinate are far, the nearest filter will be less accurate.

