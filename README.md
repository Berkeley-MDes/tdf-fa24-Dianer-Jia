# Week 5: Report 5

## Week of 10/03/2024

This was my first time using the Photon 2, and I tried to control the LED blinking through code. Here's a summary of what I did:

I started by setting up the circuit according to the image provided in the folder. (While matching it with the code, I noticed an error in the image—specifically, the white wire connected to the LED should be inserted into the D7 pin, not D3. I corrected this when building my circuit.)

<img width="800" alt="photon" src="p1.jpg">

After creating a new project in VCS as per the tutorial, I tested the file called `04_make_it_blink`. Once I entered the code and connected my Photon, I compiled and flashed it.

<img width="800" alt="photon" src="p2.jpg">

When the code ran, I saw that the LED started blinking. Pressing the button changed the blinking frequency, with the periodicity being a random value between 300 and 1000.

*** Click and watch the video

[![Watch the video](https://img.youtube.com/vi/4ag49ddaypU/0.jpg)](https://youtu.be/4ag49ddaypU)

I then tried changing the `periodicity` variable to a range between 100 and 2000.

<img width="800" alt="photon" src="p3.jpg">

After reconnecting the circuit, I found that this change didn’t make much difference—just that the blinking frequency changed from a random value between 300-1000 to one between 100-2000.

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/6MM1Dsa1wFY/0.jpg)](https://youtu.be/6MM1Dsa1wFY)

Next, I wanted to change the circuit. I aimed to add a button to control the entire circuit—pressing the new button would make the LED blink as per the original code, and pressing it again would turn off the LED completely. I connected a new button and resistor, with one side of the button connected to the D3 pin and the other to GND.

<img width="800" alt="photon" src="p4.jpg">

Not being too sure about the coding part, I asked ChatGPT to help modify it for me.

<img width="800" alt="photon" src="p5.jpg">

<img width="800" alt="photon" src="p6.jpg">

<img width="800" alt="photon" src="p7.jpg">

But I found that this new button didn’t work as I expected. I kept modifying the circuit, trying different connections, but nothing worked—the newly added button just didn’t do anything. (I also made various attempts to change the wiring, but I didn’t capture all of them; nonetheless, none achieved the desired effect.)

<img width="800" alt="photon" src="p8.jpg">

<img width="800" alt="photon" src="p9.jpg">

After two hours of attempts, I gave up and decided to ask classmates and the teacher for help during the next class to see where the problem was.

I then moved on to compiling and flashing the next file, `05_make_it_blink_outside`. Following the code, I realized I needed to connect another LED to my circuit, so I added a new LED and resistor, with one side of the LED connected to the resistor (and D3 pin) and the other to GND.

<img width="800" alt="photon" src="p10.jpg">

After compiling and flashing the code, I saw that both LEDs blinked simultaneously at the same frequency, with the button controlling the random speed of their blinking.

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/YpHS383OWrI/0.jpg)](https://youtu.be/YpHS383OWrI)

I then modified the code so that one LED was set to HIGH while the other was set to LOW, and vice versa.

<img width="800" alt="photon" src="p11.jpg">

This resulted in the LEDs alternating their blink. The yellow LED (`led_out2`) stayed on longer because, in the modified code, `led_out2` in the HIGH state had no delay control.

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/-TpIommmuXk/0.jpg)](https://youtu.be/-TpIommmuXk)

I added a delay of 500 milliseconds after `digitalWrite(led_out2, HIGH)`.

<img width="800" alt="photon" src="p12.jpg">

With this change, the yellow LED (`led_out2`) stayed on longer due to the 500 milliseconds of delay while it was in the HIGH state, while the green LED (`led_out`) remained on for only 100 milliseconds. As a result, the green LED would light up for 100 milliseconds before turning off, while the yellow LED would stay on for 500 milliseconds before turning off.

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/v77Pw_rOwRs/0.jpg)](https://youtu.be/v77Pw_rOwRs)

After this, I moved on to compiling and flashing the third file, `06_publishing_info`. In this file, I mainly observed the constantly updating information in the terminal by typing “particle serial monitor --follow.”

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/lKnDGrc5Na0/0.jpg)](https://youtu.be/lKnDGrc5Na0)

Every time I pressed the button, the rate at which the characters were generated would change randomly between 1000 and 2000 milliseconds.

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/5Lr92vuwN94/0.jpg)](https://youtu.be/5Lr92vuwN94)

I then changed the `periodicity` to 500 (I originally intended to change `void change_period(void) { periodicity = random(1000, 2000); }` but instead altered `int periodicity = 2000;`).

<img width="800" alt="photon" src="p13.jpg">

With this change, I observed that the LEDs alternated their blinking faster, and the character printing frequency in the terminal also increased.

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/q57Cteq_nRA/0.jpg)](https://youtu.be/q57Cteq_nRA)

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/X8qCsSHGWW0/0.jpg)](https://youtu.be/X8qCsSHGWW0)

**Reflection on the Circuit and Coding System**

**How the System Works Together**

While working with the circuit and Particle code, I saw how the parts fit together. The timing system controlled the LED blinking, and the code variables like button_pressed and periodicity influenced behavior — whether the LED flashed or how fast it blinked. Everything — from the circuit to the serial logs and cloud updates — creates a cohesive loop of control and feedback.

**Benefits for New Designs**

This system is flexible and modular, so it’s great for trying out new ideas. Changing the code or adding components like another LED or button was quick, which makes it easier to test new functions. Sending data to the Particle cloud adds real-time monitoring and analysis, which can be helpful for smart devices or interactive projects.

**Entry Points and Advantages**

The main entry points are hardware (building the circuit), software (coding on VCS), and cloud (data logging). The advantage is how seamlessly these work together, letting you build, test, and see results quickly. Compared to other systems, it’s easy to experiment and adjust quickly, while still getting data logged for deeper insights.

**What Ecosystems Are Missing?**

What’s missing in my daily life is a connected system that tracks my work habits and gives instant feedback — something that could monitor my productivity across all devices and suggest changes in real-time, like when to take breaks or turn off distractions.

**Connections to Other Systems**

This circuit system is a lot like my work-productivity ecosystem map. Just like the Particle code uses timers to blink LEDs, my apps send notifications to drive my tasks. A button on the circuit is like clicking "done" in a task app, and the serial logs track progress similar to how a task manager does. Seeing these connections makes me think about how I could use something similar to automate parts of my daily routines, like a hardware button to log time spent on tasks or adjust my work environment.

# Week 4: Report 4

## Week of 09/26/2024

For this week, I mainly focused on mapping my daily ecosystem. What I chose is to do a “Work & Productivity Ecosystem” map since I’m familiar with this and it is mainly what I’ve been doing since I started the MDes program. The followoing image is the map I created.

<img width="1500" alt="ecosystem map" src="ecosystem map.png">

### Description

This ecosystem map centers around the laptop as the primary device for managing work tasks and communication. It illustrates how various platforms, applications and tools—such as task management apps, calendars, cloud storage, collaborative apps, video conferencing, and a mobile phone—are interconnected.

- The laptop serves as the core, where tasks are created, updated, and managed using a task management platform.
- The calendar syncs with the task management platform, updating with deadlines and reminders, which are also accessible on the phone.
- Cloud storage provides a backup for task data and files, making them available across devices and to the collaborative app for team collaboration.
- Video conferencing improves real-time communication and project updates, feeding back into task management and scheduling.

The feedback loops show how tasks, updates, and reminders move  between devices and platforms, enabling real-time collaboration and information sharing. This ecosystem supports productivity, ensuring tasks, deadlines, and team collaboration are organized at the same time.

### Reflections

Mapping my digital ecosystem helped me see how interconnected my daily tools are, particularly how information flows between platforms like cloud storage, task management, and collaborative apps. It showed me how each tool enhances overall productivity.

### Speculations

As AI continues to integrate into daily platforms, I think that there will be smarter management for scheduling, task prioritization, and real-time collaboration. In the future, I’ll probably dive deeper into using the more advanced features of the tools I use now, aiming to automate more tasks and make sure all the platforms work together smoothly.

### Industry Insight

The rise of “Super Apps” like WeChat and Alipay could transform digital ecosystems, integrating services like messaging, payments, and e-commerce into one app, potentially simplifying workflows and changing how we interact with multiple platforms now. In the future, all the platforms and applications that I mapped today may simply just combined into one app, and improve the efficiency of work and study.

[News on “Super Apps”](https://www.boxo.io/blog/most-popular-superapps-in-the-world)

# Week 3: Report 3

## Week of 09/19/2024

### 

This week, I have been working on Project 1.

I created a total of three cellphone stands. In the first cellphone stand design, I mainly built a box and then added several spheres. By adjusting the positions of the spheres to achieve the desired effect, I used Solid Union to combine them and then carved out a groove.

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/1ZtOSspVElo/0.jpg)](https://youtu.be/1ZtOSspVElo)

Next, I used a 3D printer for the first time to print out this model.

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/6mWTH9IC5mg/0.jpg)](https://youtu.be/6mWTH9IC5mg)

An interesting aspect of the design process was that I considered user convenience. I created a spherical hole to store earphones and a hollow sphere to allow the charging cable to pass through. However, it became clear that the charging feature did not work well.

<img width="800" alt="project1-1" src="phonestand1.JPG">

<img width="800" alt="project1-2" src="phonestand2.JPG">

<img width="800" alt="project1-3" src="phonestand3.JPG">

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/AlHOxf91MsY/0.jpg)](https://youtu.be/AlHOxf91MsY)

So, I decided to improve the model. Based on feedback from my classmates, I made the following adjustments: I built another box to provide support for the back of the phone; I raised the groove by changing its position along the Z-axis to make it higher, better accommodating the charging cable; I also extended the hole for the charging cable all the way to the bottom to make it easier to use.

I then 3D printed the second cellphone stand.

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/NyZJTkdmgEo/0.jpg)](https://youtu.be/NyZJTkdmgEo)

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/Vkp2nEFAqgk/0.jpg)](https://youtu.be/Vkp2nEFAqgk)

However, I felt the process was becoming repetitive, so I wanted to challenge myself by creating a more complex design. As someone with a design background, I tend not to focus solely on structural complexity, but more on the design itself. I wanted to keep the cheese-inspired design but change the way the stand provides support.

So, I redesigned the stand.

<img width="800" alt="project1-3" src="sketch.JPG">

I first built the basic structure of the cellphone stand using three boxes, which I merged using **Solid Union**.

Next, I created a polygon, extruded it to the desired height, moved it to the ideal position, and used Cap Holes to close the geometry. To allow the triangular prism to serve as a support for the stand, I wanted to rotate it along one of its edges. I used List Item to select one edge, then used End Points and Vector 2Pt to convert the edge into an axis, which I connected to Rotate 3D for rotation. After that, I repeated my first design steps, continuously creating spheres and using Solid Difference to carve out the cheese-like shape.

**Click & Watch the video:**

[![Watch the video](https://img.youtube.com/vi/bUB6-bJzmjM/0.jpg)](https://youtu.be/bUB6-bJzmjM)

To ensure the phone could be properly supported, I had to make sure the cheese was positioned correctly. With the phone case, the phone's thickness is 1.2mm. After multiple measurements, I found a simpler method by using Rhino’s Distance tool to simulate the phone’s placement.

<img width="500" alt="project1-4" src="distance to measure.png">

To provide better support for the phone, I added another triangular prism to the top of the cellphone stand (even though I wasn’t sure if it would work). So I created another polygon. However, to meet different support needs, I used Scale NU to adjust the lengths of the polygon’s sides, making it no longer an equilateral triangle. After extruding, rotating, and other operations, I baked the model and performed a Boolean Union in Rhino. This is my final model.

<img width="800" alt="project1-5" src="final model.png">

<img width="800" alt="project1-5" src="phonestand showcase.png">



# Week 2: Report 2

## Week of 09/12/2024

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
