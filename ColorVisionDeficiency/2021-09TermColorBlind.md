# Sep 20, 2021 

Hi Bruce @bruce-usab and @mbgower 

I also responded BRIEFLY in the pull request with specific change requests...  #2034 

### The Term "Color Blind"

Before I get into "technical stuff" I want to mention an agenda item I want to discuss for on the LVTF, namely the term "color blind" ... I am hoping we can start normalizing something that is more accurate, as 99.98% of CVD types are **not color blind,** they are color limited. But they still see colors.

EDIT \>\>\>\>: Deutan, protan, tritan are color vision _deficient_. Achromatopsia, blue cone monochromacy, are color **_blind_**, and normally are also co-morbid with low vision and photophobia.
Deutan, protan have "low color vision", but also normally have good or **_better than normal_** visual function overall.
\<\<\<\<

_AS SUCH_, I suggest that line in the PR say something like

_"sometimes, though incorrectly, referred to as color blindness"_ 

or perhaps (my preference but longer) 

_**"formerly referred to as 'color blind', though in fact the vast majority of color-limited vision types do differentiate at least some colors"**_

## Some Additional Technical Comments:

<s>For the first line (18) in the PR, can we add "_...so long as luminance contrast is high enough to support rapid reading._" the suggested edit of the first line then reads:

**For people without color deficiencies, hue and saturation have minimal or no effect on legibility so long as luminance contrast is high enough to support rapid reading** _(Knoblauch et al., 1991)._

**Because:** the issue is a bit more complicated, and there are definitely color combinations that can impact readability, particularly when there is insufficient luminance contrast. The line I suggest above helps to clarify and is echoed also by Legge in his Psychophysics of reading, IX.</s>

**_Scratch this, see the new post below for why._**

### Second Line (19)
It reads "Color deficiencies can affect luminance contrast somewhat." 

Can we change to: 
**_"Color deficiencies can affect luminance contrast in some cases, as can other impairment types."_** 

Actually nearly all forms of CVD have otherwise normal vision and normal contrast, the notable exception being BCM (which may soon be removed from the CVD classification). CVD do suffer in contrast for the color area they are deficient, such as protan having poor contrast in reds.

Deutans (by far the most common) have an essentially normal CS as they have L and S cones that cover the same spectral area as normal vision. Their deficit is in M cone which limits their differentiation of colors that require the M cone or the M+L opponent process.

And also: many impairments affect contrast, IMO should be mentioned as noted.

### CVD
I don't want to get _too_ deep into whether or not any CVD types are functionally assisted with 1.4.3 or 1.4.6. In a classical design sense, body text should be about 10:1, regardless of CVD or not. The 4.5:1 ratio allows pure red `#F00` against black `#000` to pass, but this is actually a fail for someone with protanopia as I discuss in this article:

#### [_The Lighter Side of Dark Backgrounds_](https://gist.github.com/Myndex/c30dba273aa5eca426ad9f5200917c9d)

The main upshot is that adequate luminance contrast is needed by ALL sighted readers, and the 2.x contrast method does not do anything "special" to specifically assist any particular CVD type, as I discuss in the above article with demonstrations.


### BCM
And Blue Cone Monochromacy is not assisted in any real way with 1.4.3 or 1.4.6. BCM needs assistive technologies as they are co-morbid with low vision, not to mention photophobia. For visual readability, need at a minimum to modify or adjust their screen. Moreover, a page design that is using blue to help add discrimination for a protan or deutan, will negatively affect what BCM sees, outside of a custom CSS style sheet.

I suggest removing any claims of assisting Monochromacy because that is unsupportable.


### Middle Grey & Colors
> _(3) is it worth it to add mention that of the 2.8x10^14 RGB pairs, X provide contrast of 4.5:1 or higher?_

I'm on record separately, and with supporting empirical evidence that I made publicly available, that a large proportion of the color pairs that "succeed" under 1.4.3 should instead fail.

I would like to suggest that selling a point that is not actually accurate should be avoided.


### On the subject of "three way":
> _account for 3 layer contrast (A contrasts with B that contrasts with A and C)_

Unfortunately, the way that manifests in 1.4.3 is neither helpful for readability nor design. Yes, multi-level colors is needed in design, and can be accommodated on an sRGB display. The "three way" using 4.5:1 promotes a middle grey that is too dark, and not actual middle grey, and certainly not middle contrast, on an sRGB display under typical viewing conditions.

The high spatial frequency of body text is not well served by 4.5:1. Meanwhile, a large block of color on a ` <div> ` or ` <button> `does not usually need anything as high as 4.5:1 (the TEXT does, but the shape does not).

The point is that "three way" in a manner that is useful for design is best achieved by looking at the contrast needs for the specific element.


**_MOREOVER_**
The colors that 1.4.3 contrast most often does a "false pass" are the darker pairs, again as illustrated in the above linked article. When 2.2 was moving forward, I had been working on some possible SCs to address some of this, though was too swamped getting APCA ready for Silver. One of those unfinished SCs was:

**"One of the two colors of a color pair must be lighter than #A0A0A0"** 

As a interim measure to help fix some of the more serious problems with poor contrast on some websites that still pass WCAG 2.x.


## TL;DR

- Can we avoid using "color blind" as part of a push to re-label is as "color limited vision" ?
- Can we change the first line to indicate that best reading needs high enough luminance contrast?
- I generally maintain my objections (since April 2019) regarding the efficacy of WCAG 2.x contrast. 
- I'm not quite sure what's going on here with the out of the blue comment in #695 regarding two year old posts that were nevertheless privately discussed in 2019 yet are not aware of the last two years of developments. I'll save that for Thursday.

Thank you!

Andy


_Andrew Somers_      
_AGWG Invited Expert_      
_Myndex Color Science Researcher_
