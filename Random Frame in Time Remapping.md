# Random Frame in Time Remapping

---

## tag: after_effects/expressions

```
fr = 5; // Frame rate, if set to 0 (zero), then one frozen frame will be displayed;

numFrames = 15; // The number of frames from the sequence to be used

seedRandom(index,true);

seg = Math.floor(time*fr);

f = Math.floor(random(numFrames));

for (i = 0; i < seg; i++)

f = (f + Math.floor(random(1,numFrames)))%numFrames;

framesToTime(f);
```