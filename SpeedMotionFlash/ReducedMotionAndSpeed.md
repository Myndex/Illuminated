# Dec 7, 2020
## Post in CSS, prefers-reduced-motion leads readers to all animation should stop #5594

Just to chime in here on this issue, and a tangential one, as while excess motion can indeed be a problem for some people, there is also a reverse corollary.

Computers are now so fast that some changes in visual content happen in mere milliseconds, i.e. at a 60 Hz refresh rate, one frame or cycle is under 17ms. At this speed, a change can easily go unnoticed, and especially for those with vision impairments. Non-motion animation such as fade or blend transitions can help here, a well as other signaling methods.

I bring this up because it is once again an example of how accommodating needs are often conflicting. 

### _How Fast is Fast_
When editing a film, we commonly double-cut action, meaning when we make a cut in the middle of movement, we overlap the movement by four to five frames. At 24fps, this is about 160 to 200 ms, about the time it takes for the eye-brain visual system and cognition to recognize and settling into the abrupt change at the cut. The result is the action looks and feels smoother, whereas if the action was cut so it was realtime (same position of movement on the A and B side of the cut) it would tend to feel more jerky or even sped up (in fact that's an alternate editorial technique, undercutting so that some action is intentionally skipped to increase apparent speed).

This phenomena is more prevalent on the big screen in a theater than on a small video screen, though certainly noticeable on a 60" home theater screen.

### _State Change and Feedback_

One key point here is making a distinction between _distracting_ and _enabling_ animation feedback.

An animation in an unrelated advertisement obviously falls under distracting. Also distracting would be blinking or self-moving  elements intended to get you to click or follow a particular path unrelated to your current task. And yes these should be able to be shut off by the user. But these examples need to be separated from state-change feedback that is directly related to the content and/or task.

Certain cognitive/attentional issues certainly need the _distractions_ turned off, but these same individuals ALSO may need the appropriate state-change feedback that is related to their current task _turned ON_. This is also an area where haptics and physical-object-model interfaces are very helpful. 

Sound can play a useful alternate here too. Anecdotally, the sound failed on one of my laptops. Without the tiny feedback sounds of the OS, and coupled with my low vision issues (not to mention attention) I found I was constantly missing state changes, including loading whole documents with one of the text editors I use.

I literally do not see the change when it is ultra fast unless the change is high contrast and right in my fovea (central vision). Lower contrast peripheral changes go unnoticed unless that have either very high contrast or are timed to take  longer. 

### _TL;DR:_

The point then is that if important state change and feedback animations are turned off, they may need to be replaced with an alternate to enable the same level of engagement and accessibility. And one of many areas where no single solution solves everyone's needs.


_Andrew Somers_     
_W3 WAI Invited Expert_     
_Color Science Researcher_     
