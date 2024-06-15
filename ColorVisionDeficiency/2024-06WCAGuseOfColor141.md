## June 14, 2024
From PR https://github.com/w3c/wcag/pull/1788

I saw something in the meeting minutes that I believe needs to be addressed, hopefully this is the place to do so.

## Regarding lightness, color, and visual function
<details><summary><b>Click for CIE definitions and links</b></summary>

.
Definitions: The CIE is the authoritative reference for color terminology. 

The most recently revised glossary provides two definitions for the word "color" by itself, and a number of compound definitions:

> ### [**color, \<psychophysical>** ](https://cie.co.at/eilvterm/17-23-001)   
> specification of a [colour stimulus](https://cie.co.at/eilvterm/17-23-002) in terms of operationally defined values, such as three [tristimulus values](https://cie.co.at/eilvterm/17-23-038)

And

> ### [**color, \<perceptual>, perceived color**](https://cie.co.at/eilvterm/17-22-040)   
> characteristic of [visual perception](https://cie.co.at/eilvterm/17-22-082) that can be described by attributes of [hue](https://cie.co.at/eilvterm/17-22-067), [brightness](https://cie.co.at/eilvterm/17-22-059) (or [lightness](https://cie.co.at/eilvterm/17-22-063)) and [colourfulness](https://cie.co.at/eilvterm/17-22-072) (or [saturation](https://cie.co.at/eilvterm/17-22-073) or [chroma](https://cie.co.at/eilvterm/17-22-074)) --- **_Note 1 to entry:_** Perceived colour depends on the [spectral distribution](https://cie.co.at/eilvterm/17-21-029) of the [colour stimulus](https://cie.co.at/eilvterm/17-23-002), on the size, shape, structure and surround of the stimulus area, on the [state of adaptation](https://cie.co.at/eilvterm/17-22-015) of the observer's visual system, and on the observer's experience of the prevailing and similar situations of observation.     

But an important definition of color is the specific achromatic color:

> ### achromatic colour, <in the perceptual sense>
> perceived [colour](https://cie.co.at/eilvterm/17-22-040) devoid of [hue](https://cie.co.at/eilvterm/17-22-067) --- _**Note 1 to entry:**_ The colour names white, grey and black or, for transmitting objects, colourless and neutral are commonly used in relation to achromatic colour.

**In other words, the _broadest_ term "color" can have "no colorfulness."**

_SIDE NOTE: I recognize that the terminology surrounding light and color is confusing and a big part of the problem towards understanding._

- - - - - 
</details>


**The _broadest_ use of the term "color" includes a color with "no colorfulness."**

Is the broadest definition of color as "lightness, hue, and colorfulness" the same "color" that is mentioned in 1.4.1? There is a reductio ad absurdum here: If 1.4.1 means not only hue and saturation, but _also_ _lightness_, then nearly all websites fail. Text is most often displayed as _only_ a difference in lightness/darkness, and even black and white line drawings would fail, or greyscale photos.

### _Therefore this cannot be the meaning of 1.4.1_

Instead, let's examine the three aspects of color:

1. [Lightness](https://cie.co.at/eilvterm/17-22-063)/darkness/[brightness](https://cie.co.at/eilvterm/17-22-059) (perception of luminance)
2. Uniqueness (perception of [hue](https://cie.co.at/eilvterm/17-22-067))
3. [Colorfullness](https://cie.co.at/eilvterm/17-22-072) (perception of saturation/chroma)

And what is important to us, is how the human vision system processes each. After the three LMS cone types absorb light, a matrix of cells converts the three cone signals to a red/green opponent (a), a yellow/blue opponent (b), and a **_separate_** lightness/darkness opponent (L) which holds fine details, and is critical for text.

<img alt="Cones and Opponent_colors, starting with representations of the retinal cones on the left, and those signals being processed into the opponents mentioned in the text" src="https://github.com/w3c/wcag/assets/42009457/f7d62364-ef84-49be-a6cf-6984c8652de0" width="240">



Lightness (our _perception_ of luminance) is processed separately from hue and chroma. Variations in lightness are fundamental to vision. Individuals with color vision deficiency are frequently _more capable_ at detecting lightness contrasts than standard vision.

In terms of accessibility, it is hue that is the biggest concern, followed by chroma (the amount that a hue is different than neutral grey). Reading 1.4.1, it's hard to see how to apply it to anything other than hue/chroma. 

<details><summary><b>Click for More on Why 1.4.1 is About Hue/Chroma and not Lightness</b></summary>

.

Standard trichromatic human vision, with LMS cone types perceives four unique hues of red, yellow, green, blue, with secondaries purple, magenta, orange, cyan. 

Typical dichromatic vision (LS or MS) effectively perceives blue and yellow, some studies indicate a heightened sensation of saturation, but otherwise a significant limitation distinguishing the standard four unique hues. Dichromats tend to use the _luminance differences of colors_ to aid in differentiation.

In the example below, we see that the natural lightness differences of red and green mean the difference is distinguishable to all in this case. But notice that the lack of lightness difference between green and yellow (for the protan) makes green and yellow indistinguishable.

<img width="540" alt="RedGreenYellowProcessedCVD for example's upper left is standard version followed by various versions of CVD" src="https://github.com/w3c/wcag/assets/42009457/bdef73ec-3a21-46e0-b725-e433ebc47856">

And Lightness/darkness is distinctly different from hue/chroma as far as our visual function is concerned. "Saturation" is chroma divided by lightness, so yes you can say that lightness is an aspect of color per se. But as far as visual function, lightness and hue are very separate.


- - - - - 
</details>

----
> * _if you rely purely on color (meaning the change/difference is below 3:1 contrast, as per the note in the understanding for use of color that talks about contrast https://www.w3.org/WAI/WCAG22/Understanding/use-of-color.html#intent) to convey information - which does include "conveying the state of something" - then you fail use of color_

I've been given the notion that what is written in the understanding document is not "normative" — or is it? The understanding document seems to change a lot after the SCs become recommendations.

That said, there is no science to back up the assertion that 3:1 is needed to define a state change. At best, the 3:1 defined in WCAG 2.x is a reference to a 1980s era standard for text on monochrome displays, but otherwise lacking in evidence—[Dr. Arditi's 2017 paper ](https://jov.arvojournals.org/article.aspx?articleid=2628138) discussed the problems with using contrast math as a guideline.

More to the point, sticking the 'ol 3:1 into SCs because it happens to by lying around, does not make it useful nor correct.

### What's missing in 1.4.1

What is actually important, and what should be focused on in 1.4.1, is the ability to _discriminate_ between two items of information.

For items that are adjacent or near adjacent, a lightness difference creates a luminance contrast sensation. The actual amount of lightness contrast needed is dependent on the spatial characteristics of the element, which is generally not accounted for in WCAG 2.

But for items that are spaced apart, or completely independent, a lightness change without an adjacent reference, must be **_substantial_** to be easily recognized. This is true for all vision types, because by itself, a grey is neutral and not unique.

If 1.4.1 is to be helped, then some discussion of adjacent/near adjacent vs distant or isolated items would be a good step in the right direction. 

### Focus Indication

The nature of the indicator: spatial, luminance, difference from the surrounding, and near by comparisons to similar but un-focused elements, all together dictate what is needed here. As a multi-axis set of conditions, a specific _normative_ statement is elusive.

- a 1px outline close to a button needs to be nearly maximum luminance contrast to be reliably readable.
- a 4px outline, especially with a 2 px space from a button, works with less than 3:1 contrast.
- But a 4px outline around every button, where the only change is from green to yellow, can be a non starter, and needs evaluation for CVD issues. 

<details><summary><b>Click for additional examples and visual simulations of CVD</b></summary>
.

- For another example, red `#ff2200` and dark green `#004400` meets the 3:1 criteria, but for someone with protanopia, the difference in invisible even with adjacency as in the below example:

<img width="680" alt="red or green focus ... upper left is standard version followed by various versions of CVD" src="https://github.com/w3c/wcag/assets/42009457/9dd133e1-93ee-4998-9e39-7e53f3c3b30c">

----
- In the following, the same colors but increasing the focus border width 50% to 6px:

<img width="680" alt="red or green focus ... upper left is standard version followed by various versions of CVD - this version with a thicker border for focus" src="https://github.com/w3c/wcag/assets/42009457/a091cb88-124e-4a7a-b9b8-8a0f889e2a8e">

The 50% thicker border is helpful for the white buttons, as the border itself registers are 50% thicker. But the dark buttons may still be challenging, because the button is close to the luminance of the border, and so the 2px increase in border thickness is a much smaller percentage of change to the total dark area of the button.

- - - - - 
</details>

----

## TL;DR

I came here initially just to say that lightness or luminance contrast does not belong in 1.4.1, which should be referencing hue and chroma. Lightness plays a part here only insofar as it affects saturation or the perceived colorfulness.

Otherwise, lightness (luminance) is processed in our brain separately from hue and chroma, and for accessibility reasons should also be handled separately. The place to handle lightness differences or contrast is in a guideline with a perceptually uniform contrast metric.


### References
- The [CVD simulator](https://www.myndex.com/CVD) as used above.
- [Overview of perceptual contrast and color](https://www.smashingmagazine.com/2022/09/realities-myths-contrast-color/), with further references.
- [Linktree of related resources](https://linktr.ee/Myndex)


