# FSD Beta 10.12 Release Notes

- FSD Beta 10.12 

Upgraded decision making framework for unprotected left turns with better modeling of objects. Response to ego actions by adding more features that shape the go no go decision. This increases robustness to noisy measurements while being more sticky to decisions within a safety margin. The framework also leverages median safe regions when necessary to maneuver across large turns and accelerating harder through the maneuvers.

And required to safely exit the intersection.

Wow, sounds like a pretty serious upgrade for unprotected lefts.

Will be interesting to see what Chuck Cook thinks of this one.

Improved creeping for visibility, using more accurate lane geometry and higher resolution occlusion detection. So occlusion is when something is blocked so.

And required to safely exit the intersection.

Basically, the creeping is better, it handles.

Things being blocked better.

That sounds pretty good. Reduced instances of attempting uncomfortable turns through better integration with object future predictions during lane selection. Uncomfortable turns. I wonder what exactly they mean by that, I mean.

There's definitely a lot of uncomfortable turns, but what what exactly? They mean by uncomfortable are they talking about like?

Jerkiness or like you have to stop suddenly.

So I'm not sure upgraded planner to rely less on lanes to enable maneuvering smoothly out of restricted space. That sounds interesting, increase safety of turns with crossing traffic by improving the architecture of the lanes neural network, which greatly boosted recall and geometric accuracy of crossing lanes.

Improved the recall in geometric accuracy of all lane predictions by adding 180,000 video clips to the training set. Reduce traffic control related false slowdowns through better integration with lane structure.

Reduce traffic control related false slowdowns through better integration with lane structure and improved behavior with respect to yellow lights.

There are definitely some issues with the yellow lights, like one really stupid issue that I've noticed is like.

Sometimes it'll.

Cross a yellow light, but right before it finishes crossing the intersection, it'll turn red and then it just stops in the middle of the intersection and you have to press the accelerator and it's like OK. That was really stupid. So definitely like some improvements that could be made there in the control code, so that's exciting to see.