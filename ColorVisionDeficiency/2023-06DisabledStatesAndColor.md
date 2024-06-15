## June 25, 2023
*Are the disabled and readonly states relevant for SC 1.4.1? #2308*

> ..._In regard to use of colour, a better way to describe it would be chromatic colour. Black, white and grey can be used for judging contrast, but are not considered colours in the chromatic sense_...

### _Yes, I agree._

It is important to recognize that the human vision system (HVS) makes a distinction between the luminance channel (lightness/darkness, without regard to hue) and the color channels (hue, meaning unique dominant wavelength, and colorfulness i.e. chroma/saturation).

Luminance and color are separated in the HVS, serve different cognitive roles, and should be separated in accessibility guidelines in general.

### "Color and Luminance are Separate"

**The HVS:**

- HVS senses visible light in three overlapping bands (LMS), and the opponent color process takes the LMS cone signals (red green blue) and converts to three axes:
    - A single axis of light to dark (luminance) which contains the majority of spatial information such as edges & fine details, and intensity information (distance from 0).
    - Two Axes of color, a red to green (a±) and a yellow to blue (b±), intersecting at grey. These hold very little spatial information, but includes intensity and discrimination information (a vector of magnitude and direction) and is _somewhat_ independent from luminance.
    - therefore HVS has a **lightness magnitude**, and a **colorfulness magnitude** with a **hue direction**, providing four unique colors (red yellow green violet) to which we can add an additional 3 to 4 _easy_ to distinguish color combos (orange cyan purple/magenta) and many variations.
    - Most CVD (color vision deficiency) have a problem with **hue direction**, but nothing else. Protan's lightness magnitude is substantially affected in reds and red related colors. Otherwise, CVD's sense of lightness magnitude and contrast is equal or better to standard vision (colorfulness magnitude may be as well, in some studies dichromates having greater saturation sensation).

- HVS processes luminance and color _**separately**_ and in different regions $(Vn)$ of the visual cortex.
    - $V1$ processes luminance which contains nearly all the spatial details (edges, fine details) and is principally responsible for our contrast perception (lightness / darkness / brightness). $V1$ processing is dependent on spatial frequency as input stimuli effectively passes through multiple bandpass filters.
    - About 70ms+ later, $V4,V8a$ process color, distinguishing different wavelengths of light as hue, and the intensity of a dominant wavelength relative to the adapted white/grey as a colorfulness aka saturation.

- Luminance and color are separate and are each used differently in later, higher level stages in the HVS and beyond.
    - For instance, the pre-lexical VWFA (visual word form area) which recognizes letter pairs or whole words, and the subsequent language processing, appears to rely on the 0.2°-2.0° visual angle bandpass luminance channel. Color (hue) is not part of this.
    - Color, as in hue/chroma on the other hand is used in _other_ areas, such as object recognition for distinguishing, such as between a green orange and a ripe orange.

### _In Short_

Luminance is good for detail and contrast, but less effective for coding information. (FAA limits luminance coding to three levels). In WCAG 2, luminance specs are related to 1.4.3 contrast—but not 1.4.1, color.

As defined, color is bad for detail and contrast, but good for coding information—except that those with CVD may have issues understanding pure-color coding, which is the entire (and only) purpose of 1.4.1.


-----

> ..._But obviously a designer wants it to be clear when a button is active and when it's not. I think we have to acknowledge that if no one can tell the difference between an active and inactive button, this is a problem for everyone, and therefore not an accessibility issue per se._...

### _Quick Tangent:_    
Interjecting a more personal opinion here: **accessibility is for everyone.** Something that is difficult for _everyone_ to operate is most definitely **still an accessibility issue**. Now, whether or not it's "in scope" for WCAG 2.x is a separate matter. I mention this as **I definitely consider it in scope for WCAG 3** and other standards.

.


---

> ..._I don't think disabled controls should be exempt at 1.4.1_...

### _Disagree_

There's no basis to include disabled controls in 1.4.1. Reducing the contrast of a disabled control is **not a use of color**, it **_is a use of contrast_**. 1.4.1 is specific to the issue of **distinguishable hue**, and secondarily colorfulness (saturation/purity). There are other SCs that cover the functions of luminance.

**See above for details for why this is the case in the human vision system.**


- - -

> ..._Yes, I am concerned with cases where the disabled element has sufficient contrasts (which is not forbidden) or no sufficient contrasts (which is allowed)_.... 

#### _Quick Tangent:_ 
As a tangent, APCA Readability Criterion provides for minimum contrast values for disabled controls, placeholder text etc. And again, what is being discussed in this thread is actually a _**change in contrast**_, not a change in color.

Defining an SC that codifies minimum parameters for meta states would be OK, but not for WCAG2 because if you want to make that kind of fine distinction, you need reasonable perceptual uniformity in your methodology. Not to mention that having some actual science to back up statements regarding meta-states would be helpful, as meta-state distinction is a very different process than reading text.


- - -

> ..._But in both cases a disabled element should be sufficiently distinguishable from an operable one, i.e. with at least 3:1 contrast or other visual characteristics_...

#### _I really wish people would stop bringing up 3:1 contrast as if it was some miracle magical number, because it isn't._ 
It has little relevance today, and is particularly irrelevant without the use of a perceptually uniform method due to the proliferation of multiple color schemes including dark mode, light mode, high contrast, daltonized, and so forth.

While we know the flawed WCAG 2.x contrast is the current thorn, it would be good if there was an **all stop** as far as promoting 3:1 as if it was meaningful. This concern incidentally extends far beyond web content and WCAG2, and misunderstanding of contrast perception and luminance is also a persistent problem in other contexts such as architectural signage.[(Arditi 2017)](https://jov.arvojournals.org/article.aspx?articleid=2628138)

- - -

> ..._1.4.11 is about adjacent colors_,...

#### _1.4.11 is About Pseudoscience_ 
1.4.11 being one of the more flawed SCs as it lacks scientific support and fully ignores the principal driver of contrast, that being spatial characteristics of the element. Of all the contrast SCs, the one that arguably _needs to consider spatial characteristics the most_ would be the one talking about non-text elements, which have the largest range of spatial characteristics.

- - -

> ..._1.4.1 is about being able to see differences between elements that do not have to touch each other_...

#### _1.4.1 Hue Are You_
1.4.1 is about distinguishing and understanding information without relying on hue.


----

> ..._I would say that it's not reasonable to expect disabled controls to meet 1.4.1, and given that 1.4.3 and 1.4.11 already codify this as an exception, then 1.4.1 should do the same thing._...

### +1 I Agree
It is not at all reasonable, nor does it necessarily confer a functional need to be addressed. Meta states are somewhat complicated and nuanced, if anything they would deserve their own SC, though I don't think that WCAG2 is the right place.



> ..._But mandating that in terms of contrast difference still requires the simultaneous or sessionally-consecutive presence of both active and inactive controls of the same type, doesn't it?_...

### _YES EXACTLY_
One problem with simply using contrast as a meta-state, is that a user unfamiliar with the interface may need a comparative example. A second issue is if the meaning or label of the disabled control is something that should be understood. Example is the understanding that is provided by knowing a form is not ready to submit, because the submit button is grayed out, etc.

Like everything else in visual perception, meta-states are extraordinarily context sensitive, and that makes trying to stick meta-state requirements into a normative (shall) SC not only difficult but potentially problematic, with unintended consequences.

And on that note, if this were to be placed someplace other than its own SC, the SC that it should be going into would be something like **2**.4.13 -- while that's specifically about focus appearance, the focus related SCs could arguably be more about meta-states in general, than just focus.

----
Thank you for reading

