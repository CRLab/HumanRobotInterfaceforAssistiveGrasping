<center>
        <p>
          <a target="_blank" href="http://davidwa.tkins.me">David Watkins <span class="glyphicon glyphicon-new-window" aria-hidden="true"></span></a>, 
          <a target="_blank" href="https://www.linkedin.com/in/chaiwen">Chaiwen Chou <span class="glyphicon glyphicon-new-window" aria-hidden="true"></span></a>, Caroline Weinberg, 
          <a target="_blank" href="http://www.cs.columbia.edu/~jvarley/">Jacob Varley <span class="glyphicon glyphicon-new-window" aria-hidden="true"></span></a>, 
          <a target="_blank" href="https://www.linkedin.com/in/ixjlyons/">Kenneth Lyons <span class="glyphicon glyphicon-new-window" aria-hidden="true"></span></a>,
          <a target="_blank" href="https://faculty.engineering.ucdavis.edu/joshi/">Sanjay Joshi <span class="glyphicon glyphicon-new-window" aria-hidden="true"></span></a>,
          Lynne Weber,
          <a target="_blank" href="http://www.cumc.columbia.edu/rehab/profile/jstein">Joel Stein <span class="glyphicon glyphicon-new-window" aria-hidden="true"></span></a>,
          and <a target="_blank" href="http://www.cs.columbia.edu/~allen/">Peter Allen <span class="glyphicon glyphicon-new-window" aria-hidden="true"></span></a><br>
          </p><p>
            </p><p style="color:#aaa; margin-bottom: 20px">Columbia Robotics Lab</p>
          </center>
<hr />

### Abstract

This work describes a new human-in-the-loop (HitL) assistive grasping system for individuals with varying levels of physical capabilities. We investigated the feasibility of using four potential input devices with our assistive grasping system interface, using able-bodied individuals to define a set of quantitative metrics that could be used to assess an assistive grasping system. We then took these measurements and created a generalized benchmark for evaluating the effectiveness of any arbitrary input device into a HitL grasping system. The four input devices were a mouse, a speech recognition device, an assistive switch, and a novel sEMG device developed by our group that was connected either to the forearm or behind the ear of the subject. These preliminary results provide insight into how different interface devices perform for generalized assistive grasping tasks and also highlight the potential of sEMG based control for severely disabled individuals.

<hr />

### Video

<iframe width="550" height="390" src="https://www.youtube.com/embed/vsJwSkVBtkY" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

<hr />

### Results

For the user study, a trial was considered successful if the user grasped an object and carried it over to the other location on the table. A failure was when the arm could not recognize the object after three attempts or if the arm failed to pick and place the object. The subject used the mouse first in the experiment consistently and therefore the success rates were much lower than the other input devices, which we attribute to an unfamiliarity with the interface. We randomly assigned placement of the sEMG device to either behind the subject's ear or on their forearm. Users who had placed the sEMG device behind their ear were slightly more successful than those who had placed it on their forearm. An object form the YCB object database\cite{YCBDataset} was assigned to each user to grasp in the final stage of the trial for each input device. Users had no difficult picking up various sized cubes but showed reduced performance with the YCB object. On average users were successful at picking up an object 94.13% of the time.

The timing results are shown in Table \ref{tab:timingdata}. The major take away from this is that most users had very little difficulty using any of the four inputs devices. The times listed under YCB object trials took much longer than those for the blocks because the time taken to calculate the grasps was so much longer than it was for the blocks. This inflated the time spent waiting to choose a grasp for the given object. Occasionally users would have difficult with the interface such as recalibration of the sEMG device or a peripheral crashing. In cases such as these the timer was reset and the subject was asked to redo the experiment.

In addition to this added grasp calculation time, users often took much more time with the YCB object because of trouble calculating any valid grasps due to point cloud error. In these circumstances we had the user rerun object recognition on the scene to attempt to find a better view of the object. Moving forward we will likely rerun vision automatically in the event that no valid grasps are found and improve our methodology for finding grasps. All four devices had similar times for all of the trials and we take this information to show that using an sEMG device is as fast or in some cases faster than using the other three input devices, and therefore validates it as a useful input device into a HitL system.

One important thing to note is that the training time for the mouse and sEMG device were the longest. The mouse time included an introduction into the system, which inflated the amount of time it took to train the user in this case. The mouse was also the first device the user had a chance to use. The sEMG device took additional time to train the user since it had to be calibrated. Training for the sEMG device also involved finding a valid electrode location, showing users the interface, and walking them through how the device would control the interface. Training users on the Amazon Echo and the Ultimate Switch took substantially less time as they were easy to use and very similar in use to the mouse. However once the user became familiar with each device the timings were all comparable.

Overall, the users understood how they were supposed to navigate the system and were aware of what the system was doing at any given point in time. From our user studies we were able to both verify that our improvements to the new system had the intended effect, and several new areas of improvement became apparent.

One lesson learned from the experiments was that displaying more of the current scene would be useful to the user, for example showing an overlaid image of the scene on top of the user interface was a suggestion given by several of the participants. Another suggestion was that showing the perspective of the objects relative to the user would have been helpful. Many users were confused by the orientation of the grasp relative to the object and found the display to be relatively counter intuitive.

<center>    
  <figure class="figure">
    <table class="table">
      <thead>
        <tr><th>Activity</th><th>Mouse 15 trials</th><th>Alexa 15 trials</th><th>Switch 15 trials</th><th>sEMG (forearm) 7 trials</th><th>sEMG (behind ear) 8 trials</th><th>Average</th></tr>
      </thead>
      <tbody>
        <tr><td>Block 1</td><td>100%</td><td>100%</td><td>100%</td><td>100%</td><td>100%</td><td>100%</td></tr>
        <tr><td>Block 2</td><td>100%</td><td>100%</td><td>100%</td><td>100%</td><td>100%</td><td>100%</td></tr>
        <tr><td>Block 3</td><td>100%</td><td>100%</td><td>100%</td><td>100%</td><td>100%</td><td>100%</td></tr>
        <tr><td>YCB Object</td><td>66.67%</td><td>80%</td><td>80%</td><td>71.43%</td><td>87.50%</td><td>76.53%</td></tr>
        <tr><td>Average</td><td>92%</td><td>95%</td><td>95%</td><td>93%</td><td>97%</td><td>94.13%</td></tr>
      </tbody>
    </table>
    <figcaption class="figure-caption">Success rate of grasping objects during each trial. Each trial occurred 15 times and shows the number of successful grasps as well as the percentage successful. </figcaption>
  </figure>
</center>

<center>
  <figure class="figure">
    <table class="table">
      <thead>
        <tr><th>Activity</th><th>Mouse (s) </th><th>Alexa (s)</th><th>Switch (s)</th><th>sEMG (forearm) (s)</th></tr>
      </thead>
      <tbody>
        <tr><td>explain interface</td><td>169.58</td><td>80.76</td><td>78.97</td><td>314.15</td></tr>
        <tr><td>user block 1</td><td>20.5</td><td>18</td><td>20.5</td><td>18.0</td></tr>
        <tr><td>robot block 1</td><td>63.7</td><td>40.87</td><td>48.05</td><td>53.01</td></tr>
        <tr><td>user block 2</td><td>33.43</td><td>23</td><td>38.5</td><td>27.3</td></tr>
        <tr><td>robot block 2</td><td>60.39</td><td>53.52</td><td>49.548</td><td>50.07</td></tr>
        <tr><td>user block 3</td><td>21.5</td><td>17</td><td>28</td><td>13</td></tr>
        <tr><td>robot block 3</td><td>61.18</td><td>60.39</td><td>74.335</td><td>68.27</td></tr>
        <tr><td>user YCB bottle</td><td>23</td><td>74.14</td><td>77.09</td><td>124.24</td></tr>
        <tr><td>robot YCB object</td><td>73.39</td><td>40.91</td><td>67.71</td><td>65.7</td></tr>
      </tbody>
    </table>
    <figcaption class="figure-caption">Average times for both the time taken for the user to select and object and grasp, followed by the time taken by the robot to grasp the object. The robot was consistent in taking roughly 50-70 seconds to execute a grasp. </figcaption>
  </figure>
</center>

<hr />

### Downloads

#### Source Code
[https://github.com/crlab/crui_mico_ws](https://github.com/crlab/crui_mico_ws)

#### Protocol
[ModifiedBoxandBlocksProtocol.pdf]({{ '/ModifiedBoxandBlocksProtocol.pdf?v=' | append: site.github.build_revision | relative_url }})

<hr />

### Citation
Arxiv link [here](#)
