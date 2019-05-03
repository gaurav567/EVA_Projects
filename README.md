# EVA_Project1

<h2>Assignment 1A</h2>
<p>Project1.ipynb is been answered with Assignment question mentioned below-:</p>
Horizontal Edge Detector
<br>45 Degree Angle Detector (either)
<br>Blur Kernel
<br>Sharpen Kernel
<br>Identity function (doesn't do anything)
<br> Note - I have strictly used 3x3 matrix while answering mentioned questions. 

<br>Colab link - https://colab.research.google.com/drive/1gV_VeeazW4Bqwgehp2mMCob7D3MvZ8d4


<h2>Assignment 1B</h2>
<h3>Q - What are Channels and Kernels (according to EVA)?</h3>
<p>A channel generally contains the same kind of information, for example, only red color, or all the vertical edges.</p>
Note - Combination of channel will also lead to some sensitive channel where thing are linked to each other.
eg-: Combination of edges lead to arc, An arc might not exist anywhere but it could be present in form of (Vertical line, Horizontal line, angle line)

<br>Kernel - Kernel is a feature extracter, filter , 3x3 matrix it is used to identify the core from different channels specified.
eg collection of peas is a channel but a single pea is a kernel.</br>

<h3>Why should we only (well mostly) use 3x3 Kernels?</h3>

<p>Their are certain reasons why 3x3 kernels are used mostly which is discussed below with examples-:</p>

<h4>1.Logic behind not using even no's</h4> As their is no concept of middle so we cannot thing of left and right part.It is difficult to make something symmentric.
<br>eg-: We cannot make traingle from 4x4 without losing pixels and the loss after using 3x3 on 4x4 is 16-9 =7 pixels which could be huge if we consider millions of kernels.</br>

<h4>2.Why not 5x5 or higher?</h4>
Suppose we are using 5X5 matrix so we want only one 5x5 to cover whole matrix or image which is 25.
But if we use 3x3 twice to cover whole image we still able to save some computation as 2 times 3x3 = 9+9 =18,
25 - 18 = 7.
So By using 3x3 over 5x5 we have optimized our approach to some extent.

<br>Another example
<br>21x21 - 1x1 = 441 parameters.
<br>3x3 over 21x21 to reach 1x1 = 90 parameters.</br>
Results in saving huge parameters,that's why we generally prefer 3x3 mostly leaving some exceptions.


<h3>How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)</h3>
<p>To Reach 1x1 from 199x199 by performing 3x3 convolution below steps will be in picture.</p>
199x199 - 197x197 - 195x195 - 193x193 - 191x191 - 189x189 - 187x187 - 185x185 - 183x183 -181x181 - 179x179 - 177x177 - 175x175 - 173x173 - 171x171 - 169x169 - 167x167 - 165x165 - 163x163 - 161x161 -159x59 - 157x157 - 155x155 - 153x153 - 151x151 - 149x149 - 147x147 -145x145 - 143x143 - 141x141 - 139x139 - 137x137 - 135x135 - 133*133 - 131*131 - similarly series will continue till 1x1(129,127,125,123,121,119,117,115,113,111,109,107,105,103,101,99,97,95,93,91,89,87,85,83,81,79,77,75,73,71,69,67,65,63,61,59,57,55,53,51,49,47,45,43,41,39,37,35,33,31,29,27,25,23,21,19,17,15,13,11,9,7,5,3,1x1 finally)
199/2 - 99.5 approx 100 layers.


<h2>References</h2>
- EVA Session-1 video.
<br>- https://www.cis.rit.edu/people/faculty/rhody/EdgeDetection.htm - edge detection concepts
<br>- https://arxiv.org/abs/1705.07049 - receptive field concepts.
<br>- Discussions(Posted on EVA forum)
<br>- youtube(Andrew ng video on edge detection) 
      <br>https://www.youtube.com/watch?v=XuD4C8vJzEQ&feature=youtu.be&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF

