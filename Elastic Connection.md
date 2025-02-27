
# Elastic Connection

[http://www.motionscript.com/design-guide/elastic.html](http://www.motionscript.com/design-guide/elastic.html)

---

```
restLength = 20;

damp = .95;

leader = thisComp.layer("leader");

fDur = thisComp.frameDuration;

currFrame = Math.round(time / fDur);

p2 = position.valueAtTime(0);

v2 = 0;

for (f = 0; f <= currFrame; f++){

t = f*fDur;

p1 = leader.transform.position.valueAtTime(t);

delta = p2 - p1;

nDelta = normalize(delta);

a = 2 * nDelta * (length(delta) - restLength) * fDur;

v2 = (v2 - a) * damp;

p2 += v2;

}

p2

```