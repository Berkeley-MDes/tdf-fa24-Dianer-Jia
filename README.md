# Week 3: Report 3

Week of 09/19/2024

### 

This week, I have been working on Project 1.

I created a total of three cellphone stands. In the first cellphone stand design, I mainly built a box and then added several spheres. By adjusting the positions of the spheres to achieve the desired effect, I used Solid Union to combine them and then carved out a groove.

(Insert video)

Next, I used a 3D printer for the first time to print out this model.

(Insert 3D printing video)

An interesting aspect of the design process was that I considered user convenience. I created a spherical hole to store earphones and a hollow sphere to allow the charging cable to pass through. However, it became clear that the charging feature did not work well.

<img width="800" alt="gh1" src="phonestand1.jpg">

<img width="800" alt="gh1" src="phonestand2.jpg">

<img width="800" alt="gh1" src="phonestand3.jpg">

(Insert video)

So, I decided to improve the model. Based on feedback from my classmates, I made the following adjustments: I built another box to provide support for the back of the phone; I raised the groove by changing its position along the Z-axis to make it higher, better accommodating the charging cable; I also extended the hole for the charging cable all the way to the bottom to make it easier to use.

I then 3D printed the second cellphone stand.

(Insert modeling video)

(Insert 3D printing video)

However, I felt the process was becoming repetitive, so I wanted to challenge myself by creating a more complex design. As someone with a design background, I tend not to focus solely on structural complexity, but more on the design itself. I wanted to keep the cheese-inspired design but change the way the stand provides support.

So, I redesigned the stand.

(Insert sketch)

I first built the basic structure of the cellphone stand using three boxes, which I merged using **Solid Union**.

Next, I created a polygon, extruded it to the desired height, moved it to the ideal position, and used Cap Holes to close the geometry. To allow the triangular prism to serve as a support for the stand, I wanted to rotate it along one of its edges. I used List Item to select one edge, then used End Points and Vector 2Pt to convert the edge into an axis, which I connected to Rotate 3D for rotation. After that, I repeated my first design steps, continuously creating spheres and using Solid Difference to carve out the cheese-like shape.

(Insert modeling video)

To ensure the phone could be properly supported, I had to make sure the cheese was positioned correctly. With the phone case, the phone's thickness is 1.2mm. After multiple measurements, I found a simpler method by using Rhino’s Distance tool to simulate the phone’s placement.

<img width="800" alt="gh1" src="distance to measure.png">

To provide better support for the phone, I added another triangular prism to the top of the cellphone stand (even though I wasn’t sure if it would work). So I created another polygon. However, to meet different support needs, I used Scale NU to adjust the lengths of the polygon’s sides, making it no longer an equilateral triangle. After extruding, rotating, and other operations, I baked the model and performed a Boolean Union in Rhino. This is my final model.

<img width="800" alt="gh1" src="find model.png">

Showcase of the 3D print

# Week 2: Report 2

Week of 09/12/2024

### 1.Make diagrams of the example files shared.

Last week, I learned some basic knowledge of Rhino modeling. This week, by learning the principles of Grasshopper in class, I began to try using Grasshopper and Rhino together.

The first basic step I learned was how to import a model from Rhino into Grasshopper. I know this might seem a bit silly, but for a beginner, that's how it is.

<img width="800" alt="gh1" src="connect rhino geometry to gp.png">

Then, I started trying to build something simple in Grasshopper to make some preliminary changes to the model, such as rotating the model in Grasshopper:

<img width="800" alt="gh2" src="trying rotate.png">

And moving it:

<img width="800" alt="gh2" src="try to move it by gp.png">

Trying shear and bend:

<img width="800" alt="gh2" src="try to shear the move object.png">

<img width="800" alt="gh2" src="try to bend the object.png">

After that, I wanted to try extruding the model in Grasshopper, but I found that it didn’t work as I expected:

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/_-SPIFKRiFM/0.jpg)](https://youtu.be/_-SPIFKRiFM)

I asked ChatGPT why I couldn't use extrude on this model, and ChatGPT's answer was that extrude is used on surfaces, with the x, y, and z axes defining the direction of thickness. But this phone stand is a 3D model, so extrude cannot be used to thicken it.

So I switched to another method by setting the surface of the model as a mesh and then connecting amplitude to adjust the thickness.

<img width="800" alt="gh2" src="assets/try to thicken the object through mesh.png">

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/RsaaJbQGdVQ/0.jpg)](https://youtu.be/RsaaJbQGdVQ)

Through my initial exploration of Grasshopper and Rhino, I discovered some basic principles of Grasshopper, so I created a diagram to explain my understanding of these principles. Although it’s not very comprehensive, it summarizes my attempts.

<img width="800" alt="gh2" src="assets/gh diagram.png">

### 2. Experiment with the files shared, manipulate the parameters and ‘bake’ some forms.

After opening the 3dm and gh files of the phone stand, I began experimenting with adjusting some parameters to figure out what changes correspond to each value and to determine the shape I wanted.

I first experimented with changing the parameters of the phone:

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/T2pt9rDimW4/0.jpg)](https://youtu.be/T2pt9rDimW4)

[![Watch the video](https://img.youtube.com/vi/2hj6hMg86AQ/0.jpg)](https://youtu.be/2hj6hMg86AQ)

Then I tried changing the parameters of the phone stand:

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/UtUWniQJGME/0.jpg)](https://youtu.be/UtUWniQJGME)

[![Watch the video](https://img.youtube.com/vi/-FW1em-v9sc/0.jpg)](https://youtu.be/-FW1em-v9sc)

[![Watch the video](https://img.youtube.com/vi/Ql4sGBcGI_c/0.jpg)](https://youtu.be/Ql4sGBcGI_c)

[![Watch the video](https://img.youtube.com/vi/0lNkcZkTMJY/0.jpg)](https://youtu.be/0lNkcZkTMJY)

By adjusting the parameters of the phone stand, I "designed" three different phone stand models and baked them out.

<img width="800" alt="gh2" src="assets/explore and adjust paras.png">

<img width="800" alt="gh2" src="assets/bake 1.png">

<img width="800" alt="gh2" src="assets/bake 1 -2.png">

<img width="800" alt="gh2" src="assets/bake 2.png">

<img width="800" alt="gh2" src="assets/bake 3.png">

<img width="800" alt="gh2" src="assets/bake 3-3.png">

The fact that multiple designs can be made by adjusting the parameters makes me feel that Grasshopper can bring more possibilities to modeling.

### 3. Experiment with generating your own basic model of a form using Grasshopper.

After learning and exploring Grasshopper for the first time, I tried to create a model myself. I haven’t fully learned how to replace the spheres in the model with other geometric shapes, but I tried using Boolean operations to combine two geometric shapes to create a model.

I first created a box:

<img width="800" alt="gh2" src="assets/3. create a box.png">

Then I created a sphere and changed its position so that part of it overlaps with the box:

<img width="800" alt="gh2" src="assets/3. create a sphere.png">

<img width="800" alt="gh2" src="assets/3. adjust sphere position.png">

<img width="800" alt="gh2" src="assets/3. adjust sphere position2.png">

I first tried using solid difference and baked two models.

<img width="800" alt="gh2" src="assets/3. use boolean - solid difference.png">

<img width="800" alt="gh2" src="assets/3. after bake.png">

<img width="800" alt="gh2" src="assets/3. after bake 2.png">

Next, I tried to create a phone stand by adding a groove to place the phone. My idea was to create a slightly tilted box that overlaps with the model and then use solid difference. But I found that I couldn’t tilt the box along one edge. I asked ChatGPT, created a deconstruct brep, connected it to a list item, and locked the axis of rotation on that edge, but I still couldn’t rotate it.

<img width="800" alt="gh2" src="assets/3. try to create void - build phone.png">

<img width="800" alt="gh2" src="assets/3. try to rotate via one edge.png">

ChatGPT suggested converting the axis of rotation into a point, so I used division to lock the rotation point, but it still didn’t work.

<img width="800" alt="gh2" src="assets/3. failure - not rotating.png">

So, I gave up. I decided not to tilt the box and just add the groove directly to the model. But I failed again because solid difference only has two inputs, which means I can only connect two breps, while I wanted to connect the sphere, the box, and then carve out the groove.

<img width="800" alt="gh2" src="assets/3. failure - sphere and void to one object, not work.png">

I asked ChatGPT again for help and learned a new component—merge. I merged the sphere with the box that had the groove carved out and then used solid union.

<img width="800" alt="gh2" src="assets/3. merge the sphere and the object with void.png">

Bake time!

<img width="800" alt="gh2" src="assets/3. final bake!!.png">

Here is the complete form I added:

<img width="800" alt="gh2" src="assets/the form I add.png">

Final product:

<img width="800" alt="gh2" src="assets/3. there it is!.png">

<img width="800" alt="gh2" src="assets/3. there it is 2!.png">

I know my model is simple, and I encountered many difficulties that I couldn’t solve by myself during the assignment. But by watching some YouTube tutorials and asking ChatGPT for better solutions, I began to gradually understand how Grasshopper assists Rhino. It allows for more flexible and convenient changes to models in Rhino. I hope I can use Grasshopper more proficiently in the future to create the models I want.

---


# Week 1: Report 1

## Week of 09/05/2024

This week, as someone who has never used Rhino before, I downloaded Rhino and started to learn how to use it. I took Dave Schultze's Rhino 7 Essential Training course on LinkedIn to learn some basics about Rhino.
I familiarized myself with Rhino's user interface and navigation tools, and then further started experimenting with some simple 2D and 3D graphics.

<img width="500" alt="rhino1" src="assets/rhino1.png">

<img width="500" alt="rhino2" src="assets/rhino2.png">

On top of that, learn some tranformation tools like move, rotate, etc.

<img width="500" alt="rhino3" src="assets/rhino3.png">

<img width="500" alt="rhino4" src="assets/rhino4.png">

I also explored some knowledge about curves, such as creating 2D graphics on curves

<img width="500" alt="rhino5" src="assets/rhino5.png">

Also the use of freeform

<img width="500" alt="rhino6" src="assets/rhino6.JPG">

Immediately after that, I learned about some basic surface modeling.
For example, modeling strategies with extruding curves

<img width="500" alt="rhino7" src="assets/rhino7.png">

This is the first time I've created a 3D model with two shapes, and it was a lot of fun!
I also learned lofting surfaces

<img width="500" alt="rhino8" src="assets/rhino8.png">

That's just part of what I'm learning. I think Rhino is a great software to explore. I come from a fashion design background, and during my undergraduate years I learned to use clo3d to model clothing. In the process of learning Rhino, I have discovered that the two softwares have some things in common, but Rhino is more widely used and has more attention to detail. I will keep learning some new Rhino skills every week and train more until I am proficient in this software.

Also I tried laser cut today! Though everything didn't go as smooth as I think (the machine I reserved was out of order and the maker pass didn't go through that quick), I still made it! 

<img width="500" alt="lasercutai" src="assets/lasercutai.png">

<img width="500" alt="lasercutting" src="assets/lasercutting.png">

# Hello DES INV 202 Student!
Welcome to your new GitHub repository! 

# Outline
[week 1](README.md#week-1-example-report-1)

week 2, etc...

---

# Github Background Information & Context
If you’re new to GitHub, you can think of this as a shared file space (like a Google Drive folder, or a like a USB drive that’s hosted online.) 

This is your space to store project files, videos, PDFs, notes, images, etc., and (hopefully, neatly) organize so it's easy for viewers (and you!) to navigate. That said, it’s super easy for you to share any file or folder with us (your TDF instructional team) - just send us the link!  As a start, feel free to simply add images to the `/assets` folder, which is located [here](/assets). 

The specific file that I’m typing into right now is the **README.md** for this repo. 
##### (💡 TIP: The .md indicates that we’re using [Markdown formatting.](https://www.markdownguide.org/cheat-sheet/)) #####
<h6> (💡 TIP 2: GitHub Markdown supports <a href="https://gist.github.com/seanh/13a93686bf4c2cb16e658b3cf96807f2"> <em>HTML formatting</em> too, including emojis 😄</a>, in case that helps!) </h6>

### :star: Whatever you write in your **README.md** will show up on the “front page” of your GitHub repo. This is where we’ll be looking for your [weekly progress reports](https://github.com/Berkeley-MDes/24f-desinv-202/wiki/3.0-Weekly-Submissions#weekly-progress-report). They might look something like this: ###

# Week 1: Example Report 1 #
## Week of 09/05/2024

This week, I designed a cool phone stand made of rocks. Check out all my cool sketches and progress photos from this week below, etc., etc....

<img width="200" alt="Cool Phone Stand made of rocks" src="assets/exampleimg.png">

---

It's time to start making this space your own! If you want to save these instructions, make a copy.  Also, feel empowered to delete everything in this README.md and start documenting! 

Excited to work with you,
your TDF teaching team

PS: let us know if you have any questions!!

PPS: 

## Quick Links, compiled here for your convenience: ##

- [TDF Wiki](https://github.com/Berkeley-MDes/24f-desinv-202/wiki) - the ultimate source for truth and information about the course and assignments
- [Google Drive Folder](https://drive.google.com/drive/u/0/folders/1DJ1b6sSDwHXX6NRcQYt10ivyQSgU0ND6) - slides and other resources
- [bCourses](https://bcourses.berkeley.edu/courses/1537533) - where the grading happens
