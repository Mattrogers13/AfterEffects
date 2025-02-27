# Loop Expression

tag:after_effects/expressions

---

[https://www.schoolofmotion.com/blog/loop-expression-after-effects](https://www.schoolofmotion.com/blog/loop-expression-after-effects)

[Download Project File and PDF Guide](https://www.schoolofmotion.com/blog/loop-expression-after-effects#)

## What is the Loop Expression?

The loop expression in After Effects. This is an example of the cycle loop type.

A loop expression does exactly what the name implies, it loops a series of keyframes. However, there’s a lot more to the loop expression than simply cycling between the first and last keyframes. Loops can help a ton when working with walk cycles, logo reveals, background design, and more.

### **Examples of Loop Expressions**

loopOut();loopIn(“pingpong”);

- loopOut();loopIn(“pingpong”);
- loopOut(“offset”,2);
- loopOutDuration(“cycle”,3);

### Loop Expression Breakdown

Not every loop expression needs a modifier. By default the loop type is cycle unless a new name is entered.

A loop expression can be broken up into 3 distinct parts: The Property, Loop Type, and Modifier. Understanding each part is important for getting the most out of your loops. So we’re going to talk about each part in excruciating exciting detail.

**Loop Property**

loopIn vs loopOut

There are technically 4 different types of loop expression properties but we’ll take about the other two at the bottom of this post. The main two properties that you will want to know about are the loopOut and loopIn properties. Both loop properties essentially do the exact same thing with one key difference:

- loopOut(); Loops beyond the last keyframe
- loopIn(); Loops before the first keyframe

Both have their own potential use-cases, but for 90% of the projects that you work on you’ll want to use the loopOut property.

## **The Loop Types**

Not all loops are created equal. There are actually 4 different types of loops that can change the way your loop works in After Effects. To change your loop type all you have to do is add “loopname” to the inside of your parentheses. Like this:

*loopOut(“pingpong”);*

Here’s a breakdown of each loop type:

### **Cycle**

The cycle repeats a series of keyframes.

**Examples:**

- loopOut(); or loopOut(“cycle”);
- loopIn(); or loopIn(“cycle”);

The cycle loop simply repeats your keyframes forever and ever. Once a loop approaches the last keyframe it will jump right back to the first keyframe. By default a loop property without a type defined will be a cycle.

### Pingpong

He’s just gonna keep dancing and dancing, forever and ever and ever…

**Examples:**

- loopOut(“pingpong”);
- loopIn(“pingpong”);

As the name implies the “pingpong” loop type goes back and forth between your first and last keyframe. From start to finish and finish to start, over and over again.

**Offset**

**Examples:**

- loopOut(“offset”);
- loopIn(“offset”);

The Offset loop type simply builds on itself by adding or subtracting the ending value from the starting value and applying the difference to your final or opening keyframes. That explanation is admittedly confusing, but just look at the example above. As you can see the offset continues the loops movement without reverting back to the original start value. In my opinion the Offset loop type is the most powerful and potentially useful loop type, but it never gets the love it deserves.

**Continue**

**Examples:**

- loopOut(“continue”);
- loopIn(“continue”);

The “continue” loop type is really specific, but it’s still pretty cool. Essentially the continue loop continues the speed/value of the final keyframe. So if your loop ended with a rotation speed of 30 degrees a second that speed would continue beyond the final keyframe. Nothing else happens, just continued inertia… forever. #NewtonsFirstLawofMotion

Nerd Alert!

*Note: You can see a visual representation of the continued motion of the loop in the graph editor (called the post expression graph) by selecting the small graph button to the left of the expression window.*

- ***Argument Modifier****

Example of an argument modifier in-action (breakdown below).

The last thing that you can add to your loop expressions is an argument modifier. While the name sounds really scary it’s actually not that difficult to understand. Essentially an argument modifier will tell After Effects which keyframes you want to loop. For example, if you had a sequence with 5 keyframes you could tell After Effects just to loop the last 2. This is done by simply adding a comma and a number.

The number tells After Effect how many keyframes should be included in the modified loop. For example, a loopOut property with a modifier of 1 will only include 2 total keyframes: the last keyframe and the one before it. Here’s a few examples so we’re on the same page:

- loopOut(“pingpong”,1); - Will loop between the last 2 keyframes
- loopIn(“offset”,2); - Will loop between the first 3 keyframes.

Modifiers are actually really easy to use once you get the hang of them. Modifiers can only be applied to the cycle, pingpong, and offset loop types.

### **Duration Loop Property**

Duration modifiers are in seconds.

**Example:**

- loopInDuration(“pingpong”,2);
- loopOutDuration(“offset”, 4);

Lastly we should talk about two different types of loop properties: loopInDuration(); and loopOutDuration();. Both properties act in a very similar way to the loopIn(); and loopOut(); properties, but with one key difference:

Duration Loop Properties will loop based on time (seconds) when an argument modifier is applied to it. (That was a nerdy sentence…)

Basically if you add a comma and a number after your duration loop property your expression will loop based on seconds instead of keyframes. I don’t find this type of loop to be very helpful in a lot of cases, but it’s there and now you know about it.

### See you Later! See you Later! See you Later! See you Later! (It’s a loop…get it?)

Hopefully you feel ready to add loops to your next After Effects project. Loops really are a fantastic tool that can save you a lot of time. If you want to learn more about After Effects or Motion Design c[heck out our blog](https://www.schoolofmotion.com/blog) where we regularly post exhilarating tutorials.