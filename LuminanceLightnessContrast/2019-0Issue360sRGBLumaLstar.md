## Circa 2019

Hi @danburzo @peteroupc @moekraft @xi 

I see this issue is still open, and it is also discussed in issue #360, and is discussed more in depth over there (this issue should probably be merged??). It is also a tangential part of #695, which is looking into more advanced contrast math.

The threshold for sRGB to Y (Luminance) is <= 0.04045 for the linear portion, as DEFINED in the IEC standard, and can be seen in the freely available ITU document: https://www.itu.int/dms_pub/itu-r/opb/rep/R-REP-BT.2380-2-2018-PDF-E.pdf

Note however, that there are some gamma encoded transforms showing coefficients for NTSC (Rec601). There is to be sure a heap-ton of confusion on this subject.

I work in Hollywood in Feature Films and Television, specifically with digital imaging. 

The original sRGB draft had math that resulted in a discontinuity. This was addressed as pat of the IEC standard, though it's possible to be "more accurate" by not rounding as they did. But the rounded 0.04045 is perfectly suitable for the purpose of the WCAG. (There is a more significant problem is how contrast rations are chosen being discussed in issue #695).

### But also quickly:

**LUMINANCE**: this is a LINEAR (straight line) value based on light measurements. It is the **Y** from CIEXYZ, where it is a normalized value (0-100 or 0-1 for black to white). It is also **L** when measuring light, either reflective or emissive. Those are normally measures as cd/m^2 AKA "nits".

**LUMA**: This means the non-linear gamma encoded Y´(Y´prime) as used in video encoded like Y´IQ. sRGB does not use LUMA, unless it is the YCC version. The R´G´B´of sRGB are tristimulus components that each have been gamma encoded. 

__L* :__ aka **Lstar** — this is "perceptual lightness" as used in CIELAB (L* a* b*) it is non-linear and based specifically on human perception. CIELAB is intended to be perceptually uniform.

**sRGB**: the "proper" sRGB transfer curve has a linearized portion (the aforementioned threshold of 0.04045 for the gamma encoded R´G´B´). However, it is very common to use a simple 1/2.2 power curve to define the gamma. The purpose of the linearized section is to prevent the math problem of an infinite slope at 0. The "proper" curve is most useful when doing transforms of the data. The simple curve is what is used by old CRT monitors and analog circuitry among other things.



-----


> I agree that this, #360, and #695 are related in that they all discuss color contrat. But they are not the same issue at all. This one is only about which term should be used: "Luminance" or "Luma".

I see, I was looking at the many posts regarding the incorrect math in the WCAG.

THAT SAID, **the correct term is LUMINANCE.** The WCAG's current contrast assessment method uses luminance. 

LUMA is not the correct term, luma refers _only_ to y prime (Y´) as used in certain video encoding types. 

-----

> Proposed response (taken from above):
> 
> Luminance is the correct term for WCAG's usage. LUMA is not the correct term, luma refers only to y prime (Y´) as used in certain video encoding types.
> There are other updates in progress (e.g. #360), but they are separate from this issue.

Yes — not sure where this is going to be referenced? if you wanted to add fo clarity: 

_LUMINANCE_ is a linear measure of light (in either relative or absolute terms), and _LUMA_ is encoded with a "gamma" curve, as such is non-linear.


-----
-----
-----
360

> > For THIS one, is someone making a pull request? because I was about to.
> 
> Yes, I am on the hook to do that, but was asked to hold off due to some rechartering issue. @alastc @awkawk is that still the case? I am waiting for the all-clear.

Hi @svgeesus 

Along with the pull request to fix the threshold in the sRGB equation, I'm thinking it would be good to remove the reference to the old working draft for sRGB. And for an up to date reference, the ITU spec "Television Colorimetry"  is both free and authoritative, as opposed to the IEC spec which is inaccessible.

sRGB on page 14:
https://www.itu.int/dms_pub/itu-r/opb/rep/R-REP-BT.2380-2-2018-PDF-E.pdf

Thank you

Andy

-----

> Interesting, I did not know that! Thanks! I'm going to update the sRGB reference on [specref](https://github.com/tobie/specref) so that new and updated specs use this automatically.

I traced back to the IEC standard,

One thing I've noticed all over the net though is a curious set of equations that suggest that sRGB to YCC should be using the 601 coefficients (... I would SO like to see if that is in the IEC standard for bg-sRGB and scRGB.) 

The Rec709 -> YCC math shows the .21/.71/.07 coefficients. (I'm starting to feel like people don't like math or something... )  I've seen sRGB to YCC using either, and on gamma encoded R´G´ B´ — something must be wrong somewhere...



----

> video has a bad habit of computing luminance from the gamma-encoded rather than the linear components. and people in general have a terrible cargo-cult tenancy to blindly use an RGB to Y equation "they found somewhere" which is derived from the NTSC chromaticity values.

Hey @svgeesus — yes I agree they do! The worst offenders are those using `(R+G+B)/3` (yikes!) But using the coefficients while gamma encoded leads to similar errors (Yet both NTSC and Rec709 specify using the coefficients _WHILE_ gamma encoded - hooray for inconsistency in technology...not).

### WCAG L Equation
For the subject of this thread, Here is the comparison between the wrong threshold value (WCAG) and the correct value, using 8bit color:

![Screen Shot 2019-06-04 at 2 32 06 AM](https://user-images.githubusercontent.com/42009457/58868625-90c88e80-8671-11e9-96a9-91dec959e4b2.png)

No errors using 8 bit — I couldn't find an _8 bit value_ that was affected by the error. Nevertheless, someday it should be addressed & corrected, as I find people using and referencing this on a fairly regular basis. 

(And to be clear to anyone else reading, this WCAG error in sRGBtoY math is _distinctly separate_ from the contrast-math problem being discussed in 695).


-----

Just to casually step over this poor dead horse: changing the sRGB linearization math to be correct instead of wrong has no  effect on results for this narrow use case, the problem is more of optics as it degrades credibility by having a known incorrect piece of math in public view. Also the trickle down of people using these wrong thresholds and using it for whatever other purpose is an annoying persistent problem.

The actual (substantial) problem with the math and methods are elsewhere, and unrelated to this error, as well established now.

**IRONICALLY**: it is this little error that first caught my attention as it leapt out at me, because I use the sRGB math (the correct one) frequently in film work. This is what caused me to dig deeper, and I wonder if I would have gotten so involved into the other "more hidden" issues if this little bit had been correct? It would not have caught my attention...  It was sort of a tip of the iceberg or something...


-----




