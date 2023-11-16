# Sept 20 2021

## REGARDING COLOR CONTRAST

I wanted to review some of the literature before commenting further on the line:

> _"...For people without color deficiencies, hue and saturation have minimal or no effect on legibility as assessed by reading performance (Knoblauch et al., 1991)."_

While I suggested a minor edit in the previous post, I wanted to comment further as that line seemed a bit askew and out of context relative to some more recent research.

Without doing a super-deep dive, but citing Legge et al from **Psychophysics of Reading XI:**

- Subjects with low vision do better with luminance contrast than with color (hue/sat) contrast.
    - This is using very large letters that subtend 6° on the retina.
    - This is approximately a 280px x-height, aka a 560px font.
- Subjects with normal vision read giant 6° letters as fast for color or luminance contrast.
- BUT Normal vision read 1° letters faster for luminance contrast than for color contrast.
    - 1° is a 45px x-height aka a 90-px font, still very large.
    - scaling the color contrast showed in overlay a similar curve to the luminance contrast, but no scaling was needed for the normal vision and 6° letters.
    - There was some discussion regarding scaling color contrast based on value over threshold, though this was not needed for the giant letters.
- Color and luminance contrast are NOT additive, so having both did not improve reading speed.
- The color contrast tested was limited to red/green. Other colors (such as red/blue which are known to be a problem) were not tested.

### There are important implications, which I discuss:

 The visual angle of a typical  16px font is about ⅓rd of a degree, or 1/6th of a degree in x-height. 

The normal vision group were tested with letter 6 times normal body text, and 36 times normal body text. The low vision group, only the 36 times letters.

### KEY TAKEAWAYS:
1) The Low Vision group did better with luminance contrast than color contrast.
2) The normal vision group did better with smaller letters and luminance contrast than color contrast, BUT normal size text was not tested, and there are important implications here.

## Spatial Frequency
We know that at higher spatial frequencies, that only luminance contrast is functional. This is because color (hue and chroma) roll off at a much lower frequency than does luminance.

The 6° letters are large enough that for normal vision, they are well within the useable CS curve for chroma contrast, thus it is not surprising that normal vision read the 6° letters similarly for both color or luminance contrast. ALSO Normal vision read the 6° letters SLOWER than the 1° letters overall.

IMPORTANTLY those with low vision did better with the luminance contrast than color, and this should be noted as a key takeaway.

The 1° letters for normal vision are still very much larger than than body text, and near the peak of the luminance CS curve. The fact that there was a shift in scale between luminance and color contrast is expected, due to the different spatial frequency responses.

**Other studies,** not to mention my own empirical studies here in the lab, show that at the high spatial frequencies of COLUMNS OF BODY TEXT i.e. 1/6th of a degree letters, that only luminance contrast is helpful for readability, and in fact some color pairs can cause excessive disability glare.

This is expected due to the frequency response of contrast sensitivity of the chromatic and luminance channels in the visual cortex.

**_SIDE NOTES:_** 6° letters are so large, they are likely recognized only as letter by letter objects, and not via the VFWA (Visual Word Form Area) as such they are read slower than 1° letters by normal vision. The range of letter sizes for _best_ readability is about 0.2° to 2° of visual angle. x-height for a 18px font is just shy of 0.2°, which is in part why I frequently **recommended an 18px font for body text.**


## TL;DR
Ultimately, I want to ask to change the line, as the way it reads it is too general and broadly states something regarding color contrast that, out of context related to glyph size, could be taken and used the wrong way.

**_We need to reinforce that:_**

- For low vision, luminance contrast is the important one. 
    - This is true of course for CVD also.
- And luminance contrast is what is important for small text such as body text.

### _Suggested new statement:_
**For people with normal vision and reading very large letters, hue and saturation have minimal effect on legibility. (Knoblauch et al., 1991) However for people with low vision, for people with color limited vision, luminance contrast is the most important for readability (Legge, Psychophysics of Reading XI). This also holds true for normal vision when using small letters such as in body text. (Barten 2003)**

Thank you


Andy
