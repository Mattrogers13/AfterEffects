# After Effects Animation Expressions
Source: https://gist.github.com/HandsomePhil/0c5b6144a6627d2e7abb9d55c0c5b5ff

The following has been curated from the following helpful links:
- [Six Essential Expressions for Creative Coding in After Effects](https://www.schoolofmotion.com/blog/six-essential-expressions-creative-coding-after-effects)
- [Motion Graphics - Quick Pop Up Tutorial In After Effects](https://www.youtube.com/watch?v=7Hnlz2A23jg)

## Bounce Expression #1
First create an animation (ie. scale 100 to 120% or position from left to right). Next apply bellow’s expression to the property you’ve key-framed to make the animation bounce.

```
n = 0;
if (numKeys > 0){
n = nearestKey(time).index;
if (key(n).time > time){
n--;
}
}
if (n == 0){
t = 0;
}else{
t = time - key(n).time;
}
if (n > 0 && t < 1){
v = velocityAtTime(key(n).time - thisComp.frameDuration/10);
amp = .06;
freq = 3;
decay = 5.0;
value + v*amp*Math.sin(freq*t*2*Math.PI)/Math.exp(decay*t);
}else{
value;
}
```

## Bounce Expression #2
If you'd like a bit more control, here is an alternative script. After copying and pasting in After Effects, you'll need to customize three parts:
- Variable e, which controls the elasticity of the bounce
- Variable g, which controls the gravity acting on your object
- Variable nMax, which sets the maximum number of bounces
```
e = .7; //elasticity
g = 5000; //gravity
nMax = 9; //number of bounces allowed
n = 0;

if (numKeys > 0){
n = nearestKey(time).index;
if (key(n).time > time) n--;
}
if (n > 0){
t = time - key(n).time;
v = -velocityAtTime(key(n).time - .001)*e;
vl = length(v);
if (value instanceof Array){
  vu = (vl > 0) ? normalize(v) : [0,0,0];
}else{
  vu = (v < 0) ? -1 : 1;
}
tCur = 0;
segDur = 2*vl/g;
tNext = segDur;
nb = 1; // number of bounces
while (tNext < t && nb <= nMax){
  vl *= e;
  segDur *= e;
  tCur = tNext;
  tNext += segDur;
  nb++
}
if(nb <= nMax){
  delta = t - tCur;
  value +  vu*delta*(vl - g*delta/2);
}else{
  value
}
}else

value
```


## Wiggle Expression
Can be applied to any property, but works great on the position to create a natural camera movement.
```
wiggle(1,50);
```

## Squash and Stretch Expression
Apply it to the scale attribute of any object. Works best on icons or bullet points.
```
maxDev = 13; // max deviation in pixels
spd = 30; //speed of oscillation
decay = 1.0; //how fast it slows down
t = time - inPoint;
x = scale[0] + maxDev*Math.sin(spd*t)/Math.exp(decay*t);
y = scale[0]*scale[1]/x;
[x,y]
```

## Motion Tail Expression
First animate the position of an object. Then apply bellow’s expression to the position:
```
delay = 5; //number of frames to delay
d = delay*thisComp.frameDuration*(index - 1);
thisComp.layer(1).position.valueAtTime(time - d)
```
And this code to the opacity:
```
 opacityFactor = .75;
 Math.pow(opacityFactor,index - 1)*100
 ```
 Now simply duplicate that entire layer (CTRL + D / CMD +D) a couple of times.
 
 ## Timer Up or Down Expression
 Create a text layer and apply the expression to the source text attribute.
 ```
 //Define time values
var hour = Math.floor((time/60)/60);
var min = Math.floor(time/60);
var sec = Math.floor(time);
var mili = Math.floor(time*60);
// Cleaning up the values
if (mili > 59){ mili = mili - sec*60; }
if (mili < 10){ mili = "0" + mili; } if (sec > 59){ sec = sec - min*60; }
if (sec < 10){ sec = "0" + sec; } if (min >= 59){ min = min - hour*60; }
if (min < 10){ min = "0" + min; }
// no hour cleanup
if (hour < 10){ hour = "0" + hour; }
//Output
hour + ' : ' + min + ' : ' + sec + ' : ' + mili;
```

