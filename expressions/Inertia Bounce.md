# Inertia Bounce

Source: [https://motionarray.com/blog/6-common-after-effects-expressions-you-should-be-using](https://motionarray.com/blog/6-common-after-effects-expressions-you-should-be-using)

---

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

if (n > 0){

v = velocityAtTime(key(n).time - thisComp.frameDuration/10);

amp = .05;

freq = 4.0;

decay = 2.0;

value + v_amp_Math.sin(freq_t_2_Math.PI)/Math.exp(decay_t);

}else{

value;

}
```