# toComp

tags:after_effects/expressions

---

[https://motionarray.com/blog/6-common-after-effects-expressions-you-should-be-using](https://motionarray.com/blog/6-common-after-effects-expressions-you-should-be-using)

[https://ukramedia.com/tip2/](https://ukramedia.com/tip2/)

[https://preview.mailerlite.com/x8o5l1/1449915593804222202/j5i6/?ml_subscriber=1449915593804222202&ml_subscriber_hash=j5i6](https://preview.mailerlite.com/x8o5l1/1449915593804222202/j5i6/?ml_subscriber=1449915593804222202&ml_subscriber_hash=j5i6)

---

### Example 1

```
layer = thisComp.layer("Null 1")
layer.toComp([0,0,0])
```

## Example 2

```
toCompVec([0,0,1])[2]
```

```
toCompVec([0, 0, -1])[2]
```

The basis for the expression is to allow you to give 3D properties to 2D effects. This is particularly useful in something like the example below, where we have a 2D layer with the 2D beam effect, but we want to have it move with the circles that are in z space.

To do this, we’ll add expressions to the Starting Point and Ending Point controls in the beam effect. The expression below is set with “Null 1” as the layer to connect to. In your own version, you’ll replace that with whatever layer you want to attach the end of the line to.

This is a perfect and easy way to create cool dynamic motion in 3D space with 2D layers.