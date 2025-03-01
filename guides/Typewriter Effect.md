# Typewriter Effect

https://www.reddit.com/r/AfterEffects/comments/y046qr/can_anyone_help_me_with_a_tutorialscript_for_this/
https://preview.redd.it/5gx370ywcws91.gif?format=mp4&s=405e5482793e824379cca808dc362472b2ba7a50

- create a textbox (by dragging, not clicking, with the text tool)
- fill it with text
- add a text animator for scale.
- the scale animator needs value 0,0 and the range needs smoothness 0 (in the advanced settings)
- animate the start of the range so the letters appear at the desired rate.
- give anchorPoint this expression:
- `value + [0, sourceRectAtTime().height];`

The fact that the text is all uppercase is a plus because then we don’t have to worry about ascenders appearing and shifting the text up a fraction of a line.