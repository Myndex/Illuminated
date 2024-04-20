### December 19, 2019
# Obsolete sRGB draft

## The 0.03928 still needs to be changed to 0.04045, and the link to the obsolete sRGB draft should be removed.

### Andy's Pedantic Ramblings on Math:
**Warning: May cause drowsiness, do not read while driving.**
FWIW: in developing the new math for silver (the first working draft of which I finally turned in today), I am using the simple exponent version, not this piecewise method for a couple reasons. The actual standard indicates the monitor uses a simple exponent (as is typically the case). Since we are attempting to _predict_ how something will be perceived, we are interested in emulating the monitor display TRC, provided nothing we are doing will have problems with the simple exponent transformation.

The "reason" for the piecewise was to prevent math problems when doing image processing on sRGB content (such as running into an infinite slope at 0). When doing processing and going in and out of sRGB space, we want to be using an invertible method, so we use the piecewise to avoid math issues, etc. 

Nevertheless, many applications use the simple exponent version for their ICC profiles (Adobe for example). 

Certainly, for predicting how something is "going to look"when displayed, using a simple exponent is often the better choice.

sRGB Monitors are specified to be ~2.2, however, research surveys show that users typically have them cranked at 2.4 or more — partly because modern displays are capable of being much brighter, so setting a display at 200nt instead of 100nt in the same ambient light, a user would likely want to increase monitor gamma to darken the display midrange for a similar perceptual intent.

As far as which specific exponent to use: 2.2? 2.218? 2.223? 2.22222? Splitting hairs, there are minor differences. I like 2.218 because it is unity with the piecewise version at # 777 (CIE Y 18.4, aka middle grey) and there are some math reasons this is useful. 

Hmmm, I'm putting _myself_ to sleep now, goodnight all...
