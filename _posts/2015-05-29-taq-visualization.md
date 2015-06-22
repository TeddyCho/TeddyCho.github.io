---
layout: post
title: Visualize Trades and Quotes
unlisted: true
---

# Tasks
> * Visualize trades and quotes (TAQ) data.
>
> * Include a comparison of continuous limit order book (CLOB) and frequent batch auctions (FBA).

# Visualization

<BODY BGCOLOR="#FFFFFF" onLoad="launch()">
  <CENTER>
    <form>
  <label for="fbaInterval">FBA Interval: </label><select name = "fbaInterval" onFocus="this.select()"  onchange="switchInterval(this.value)"> 
    <option value = "1">1 second</option>
    <option value = "120">120 seconds</option>
    <option value = "360">360 seconds</option>
</select>
    </form>
    <br>
  <IMG id="animation" WIDTH="600" HEIGHT="600" SRC="https://raw.githubusercontent.com/TeddyCho/bookVis/master/output/framesGOOGOneSec/frame0.gif">
  <BR>
    <A HREF="JavaScript: func()" onClick="decrementImage(--current_image)">
      <IMG SRC="https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/mediaControls/stepBackward.png" height="40" width="40" ALT="-1">
    </A>
    <A HREF="JavaScript: func()" onClick="stop()">
      <IMG SRC="https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/mediaControls/pause.png" height="40" width="40" ALT="Stop">
    </A>
    <A HREF="JavaScript: func()" onClick="change_mode(1);fwd()">
      <IMG SRC="https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/mediaControls/play.png" height="40" width="40" ALT="Fwd">
    </A>
    <A HREF="JavaScript: func()" onClick="incrementImage(++current_image)">
      <IMG SRC="https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/mediaControls/stepForward.png" height="40" width="40" ALT="+1">
    </A> &nbsp;&nbsp;
    <A HREF="JavaScript: func()" onClick="change_speed(delay_step)">
      <IMG SRC="https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/mediaControls/minus.png" HEIGHT="40" ALT="slow">
    </A>
    <A HREF="JavaScript: func()" onClick="change_speed(-delay_step)">
      <IMG SRC="https://raw.githubusercontent.com/TeddyCho/TeddyCho.github.io/master/_posts/img/mediaControls/plus.png" HEIGHT="40" ALT="fast">
    </A>
  <FORM METHOD="POST" id="control_form">
    <p class="control2">Frame:
      <INPUT TYPE="text" id="frame_nr" VALUE="9" SIZE="2" onFocus="this.select()" onChange="go2image(this.value)"></INPUT>
    </p>
  </FORM>
  </CENTER>
</BODY>

The above illustration shows GOOG TAQ data on the NASDAQ OMX BX exchange over two hours' time.

The bid and ask are represented by two horizontal bars whose lengths are defined by quote size.

The left graph represents the data feed in its original CLOB form. The trades are represented by yellow stars whose sizes are defined by trade volume. (Translucency and horizontal noise are added so that accumulation is observable.)

The right graph represents a simulated FBA feed. Analogous to the CLOB representation, the exchange BBO is denoted by the two bars. When an auction results in trading, the trades' aggregate is represented by a star at the clearing price, whose size is defined by aggregate volume.

# Data
The TAQ data covered the following time frame and symbols:
<table>
  <thead>
    <tr>      <th>Timeframe</th> <th>Symbol</th> <th>Exchange</th>   </tr>
  </thead>
  <tbody>
    <tr>      <td>09-July-2014</td>
      <td>GOOG</td> 
      <td>NASDAQ OMX BX</td> 
    </tr>
  </tbody>
</table>

# To Do
* Given TAQ data, simulate the FBA better. Currently, it's just randomly choosing when the auction results in a trade or not, and otherwise mirroring CLOB. Differentiate between snipe trades and investor trades.
* Consider accounting for multiple exchanges.



<SCRIPT LANGUAGE="JavaScript">

modImages = new Array();

first_image = 1;
last_image = 150;

modImages = new Array();
myFilePrefix = "https://raw.githubusercontent.com/TeddyCho/bookVis/master/output/framesGOOG1Sec/frame";
for (i = 0; i < last_image; i++) { 
    modImages[i] =  myFilePrefix.concat(i.toString()).concat(".gif");
}
 
//**************************************************************************
 
//=== THE CODE STARTS HERE - no need to change anything below ===
 
//=== global variables ====
theImages = new Array();      //holds the images
imageNum = new Array();       //keeps track of which images to omit from loop
normal_delay = 50;
delay = normal_delay;         //delay between frames in 1/100 seconds
delay_step = 50;
delay_max = 6000;
delay_min = 50;
dwell_multipler = 3;
dwell_step = 1;
end_dwell_multipler   = dwell_multipler;
start_dwell_multipler = dwell_multipler;
current_image = first_image;     //number of the current image
timeID = null;
status = 0;                      // 0-stopped, 1-playing
play_mode = 0;                   // 0-normal, 1-loop, 2-sweep
size_valid = 0;
 
//===> Make sure the first image number is not bigger than the last image number
if (first_image > last_image)
{
   var help = last_image;
   last_image = first_image;
   first_image = help;
}
 
//===> Preload the first image (while page is downloading)
   theImages[0] = new Image();
   theImages[0].src = modImages[0];
   imageNum[0] = true;
 
//==============================================================
//== All previous statements are performed as the page loads. ==
//== The following functions are also defined at this time.   ==
//==============================================================
 
//===> Stop the animation
function stop()
{
   //== cancel animation (timeID holds the expression which calls the fwd or bkwd function) ==
   if (status == 1)
      clearTimeout (timeID);
   status = 0;
}
//===> Stop the animation
function switchInterval(v)
{
   modImages = new Array();
   myFilePrefix = "https://raw.githubusercontent.com/TeddyCho/bookVis/master/output/framesGOOG";
  myFileInBetween = "Sec/frame";
  for (i = 0; i < last_image; i++) { 
      modImages[i] =  myFilePrefix.concat(v).concat(myFileInBetween).concat(i.toString()).concat(".gif");
  }
  launch();
}
 
 
//===> Display animation in fwd direction in either loop or sweep mode
function animate_fwd()
{
   current_image++;                      //increment image number
 
   //== check if current image has exceeded loop bound ==
   if (current_image > last_image) {
      if (play_mode == 1) {              //fwd loop mode - skip to first image
         current_image = first_image;
      }
      if (play_mode == 2) {              //sweep mode - change directions (go bkwd)
         current_image = last_image;
         animate_rev();
         return;
      }
   }
 
   //== check to ensure that current image has not been deselected from the loop ==
   //== if it has, then find the next image that hasn't been ==
   while (imageNum[current_image-first_image] == false) {
         current_image++;
         if (current_image > last_image) {
            if (play_mode == 1)
               current_image = first_image;
            if (play_mode == 2) {
               current_image = last_image;
               animate_rev();
               return;
            }
         }
   }
 
   document.getElementById("animation").src = theImages[current_image-first_image].src;   //display image onto screen
   document.getElementById("frame_nr").value = current_image;                //display image number

   delay_time = delay;
   if ( current_image == first_image) delay_time = start_dwell_multipler*delay;
   if (current_image == last_image)   delay_time = end_dwell_multipler*delay;
 
   //== call "animate_fwd()" again after a set time (delay_time) has elapsed ==
   timeID = setTimeout("animate_fwd()", delay_time);
}
 
 
//===> Display animation in reverse direction
function animate_rev()
{
   current_image--;                      //decrement image number
 
   //== check if image number is before lower loop bound ==
   if (current_image < first_image) {
     if (play_mode == 1) {               //rev loop mode - skip to last image
        current_image = last_image;
     }
     if (play_mode == 2) {
        current_image = first_image;     //sweep mode - change directions (go fwd)
        animate_fwd();
        return;
     }
   }
 
   //== check to ensure that current image has not been deselected from the loop ==
   //== if it has, then find the next image that hasn't been ==
   while (imageNum[current_image-first_image] == false) {
         current_image--;
         if (current_image < first_image) {
            if (play_mode == 1)
               current_image = last_image;
            if (play_mode == 2) {
               current_image = first_image;
               animate_fwd();
               return;
            }
         }
   }
 
   document.getElementById("animation").src = theImages[current_image-first_image].src;   //display image onto screen
   document.getElementById("frame_nr").value = current_image;                //display image number

   delay_time = delay;
   if ( current_image == first_image) delay_time = start_dwell_multipler*delay;
   if (current_image == last_image)   delay_time = end_dwell_multipler*delay;
 
   //== call "animate_rev()" again after a set amount of time (delay_time) has elapsed ==
   timeID = setTimeout("animate_rev()", delay_time);
}
 
 
//===> Changes playing speed by adding to or substracting from the delay between frames
function change_speed(dv)
{
   delay+=dv;
   //== check to ensure max and min delay constraints have not been crossed ==
   if(delay > delay_max) delay = delay_max;
   if(delay < delay_min) delay = delay_min;
}
 
//===> functions that changed the dwell rates.
function change_end_dwell(dv) {
   end_dwell_multipler+=dv;
   if ( end_dwell_multipler < 1 ) end_dwell_multipler = 0;
   }
 
function change_start_dwell(dv) {
   start_dwell_multipler+=dv;
   if ( start_dwell_multipler < 1 ) start_dwell_multipler = 0;
   }
 
//===> Increment to next image
function incrementImage(number)
{
   stop();
 
   //== if image is last in loop, increment to first image ==
   if (number > last_image) number = first_image;
 
   //== check to ensure that image has not been deselected from loop ==
   while (imageNum[number-first_image] == false) {
         number++;
         if (number > last_image) number = first_image;
   }
 
   current_image = number;
   document.getElementById("animation").src = theImages[current_image-first_image].src;   //display image
   document.getElementById("frame_nr").value = current_image;                //display image number
}
 
//===> Decrement to next image
function decrementImage(number)
{
   stop();
 
   //== if image is first in loop, decrement to last image ==
   if (number < first_image) number = last_image;
 
   //== check to ensure that image has not been deselected from loop ==
   while (imageNum[number-first_image] == false) {
         number--;
         if (number < first_image) number = last_image;
   }
 
   current_image = number;
   document.getElementById("animation").src = theImages[current_image-first_image].src;   //display image
   document.getElementById("frame_nr").value = current_image;                //display image number
}
 
//===> "Play forward"
function fwd()
{
   stop();
   status = 1;
   play_mode = 1;
   animate_fwd();
}
 
//===> "Play reverse"
function rev()
{
   stop();
   status = 1;
   play_mode = 1;
   animate_rev();
}

//===> "play sweep"
function sweep() {
   stop();
   status = 1;
   play_mode = 2;
   animate_fwd();
   }
 
//===> Change play mode (normal, loop, swing)
function change_mode(mode)
{
   play_mode = mode;
}
 
//===> Load and initialize everything once page is downloaded (called from 'onLoad' in <BODY>)
function launch()
{
   for (var i = first_image + 1; i <= last_image; i++)
   {
      theImages[i-first_image] = new Image();
      theImages[i-first_image].src = modImages[i-first_image];
      imageNum[i-first_image] = true;
      document.getElementById("animation").src = theImages[i-first_image].src;
      document.getElementById("frame_nr").value = i;
   }
 
   // this needs to be done to set the right mode when the page is manually reloaded
   change_mode (1);
   fwd();
}
 
//===> Check selection status of image in animation loop
function checkImage(status,i)
{
   if (status == true)
      imageNum[i] = false;
   else imageNum[i] = true;
}
 
//==> Empty function - used to deal with image buttons rather than HTML buttons
function func()
{
}
 
//===> Sets up interface - this is the one function called from the HTML body
function animation()
{
  count = first_image;
}
</SCRIPT>
