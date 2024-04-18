_April 18 2024_
# Q: In RGB model how many distinct hues are available?

## Short Answer
HSV/HSB/HSL are not perceptually uniform models, therefore they cannot provide a useful metric for "number of distinct hues".

# Longer Answer
The OP asks for "distinct" hues, which I read to mean visually distinguishable hues. This is a matter of perception, and relies on the psychophysical attributes of the human vision system (HVS).

Consider these examples, we'll be using Delta E 2000 to indicate the perceptual difference. For reference, here is the sample target at a ∆E2000 of **10** and of **20**.

<img src="https://i.stack.imgur.com/DTMml.png" width="370">

The samples were setup for essentially equal luminance and saturation/chroma, so the main difference is the hue. In the above example, the ∆E of 10 has a hue change of 21°, and the ∆E of 20 has a hue change of 60°, in LCHuv.

∆E2000 values lower than 2 are imperceivable to most people. The three samples below are each just slightly less than a ∆E of 2. (The same ampersand is in each one, just as the above examples, but at such a low ∆E it is very hard to see for most). 

Each sample below lists the two sRGB values used, followed by the **∆E**, the delta of the **dominant wavelength** in nm, and the delta of the **hue angle**, referencing LCHuv.

### Sample A
<img src="https://i.stack.imgur.com/0ATEI.png" width="370">

`rgb(14,143,146) and rgb(22,142,149)`
- ∆E2000 < 1.8
- ∆ Dominant λ 1.1nm
- ∆ Hue Angle (huv) 4.7°

### Sample B
<img src="https://i.stack.imgur.com/s2KIB.png" width="370"> 

`rgb(200,101,20) and rgb(197,103,13)`
- ∆E2000 < 1.8
- ∆ Dominant λ 1.2nm
- ∆ Hue Angle (huv) 2.0°

### Sample C
<img src="https://i.stack.imgur.com/YNHsD.png" width="370"> 

`rgb(143,105,229) and rgb(135,109,228)`
- ∆E2000 < 2.0
- ∆ Dominant λ 10.7nm
- ∆ Hue Angle (huv) 2.8°

While these three samples each have about the same ∆E, at the threshold just noticeable difference (JND) notice that each one has a significantly different change as per hue angle, and/or a significantly different change per the dominant wavelength.

## Key Takeaways

The numerical change relative to perception is not uniform over the spectrum of visible light/color.

Hue does not have an "angle" in the real world, only wavelengths, and a dominant wavelength. Hue *angle* is a mathematical convenience for working with color. The wavelength is indicated on the curved spectral locus outline of the CIE chromaticity chart:


[![CIE 1931 chart][1]][1]

And notice that the different color spaces enclose and different volume of colors. The ∆E is larger for a given code value change for the larger color spaces.

The Dominant wavelength varies from around 360nm to 700nm around the spectral locus, and the inverse, -566nm to -493nm through the line of purples. So about 340nm around the locus, 73nm across the line of purples, if we notice that ∆E2k of < 2 equates to a difference of about 1nm, we might think that there are 413 unique hues, but notice that as we get closer to the ends of the spectrum, the change in wavelength increases substantially for the same (perceived) ∆E.

So, this implies that for fairly saturated colors, of about middle luminance, there are less than 400 distinguishable hues on an sRGB display. **But in reality, much less.**

If we consider that with a ∆E less than 2, the hue angle change is 2 or more, and there are 360° available, then we'd say there are less than 180 distinguishable hues.

### But there are even fewer.

Looking at the three samples above, notice that even with a ∆E of 2, a ∆ hue angle of 2°, or a ∆ wavelength of more than 1nm, the two colors are nearly impossible to distinguish when they are immediately adjacent.

This means that if they are *not* adjacent, no difference could be seen—color differences this close need to be next to each other with no gap or border.

And then, if we are not looking at both colors at the same time, then our memory of one color to determine if a second color is the same or different, when viewed separately, so that the comparison is by memory and not continuous viewing, then we need an even greater ∆E to distinguish the colors from each other.

And then further, to use specific hues to define information (like lines on a map, or bars on a chart) we need even further separation to make the distinction clear.

### *Unique Eunichs in Pink Tunics*
The HVS has four unique colors: **Red Yellow Green Blue**. For normal vision, these are distinct. Red light and Green light mix to Yellow light, and Yellow light and blue light mix to grey (neutral) light.

In between these four unique hues, we have a set of secondary hues like orange, teal, and purple. This gives ten including white, gray, and black:

```
White     
Gray, RED, orange, YELLOW, GREEN, teal, BLUE, purple     
Black  
```

And then adding in lighter/desaturated or darker versions. For instance, pink is a desaturated lighter red. Brown is a darker orange/yellow. 

Lightness is a poor way to encode information in isolation, the FAA limits it to "three levels of lightness". But combined with hue & saturation, we can expand the recognizable colors substantially to 22 basic colors for standard vision. 

```
White
    pink     beige     SeaFoam    cyan   lt.sky  magenta
Gray  RED   orange  YELLOW   GREEN  teal  BLUE   purple
     maroon    brown    olive   forest  navy  cobalt
Black
```
For colors that are close or adjacent, and on large/thick elements these can be varied further in terms of luminance or saturation. However, for thin lines and/or small elements, hue discrimination in the HVS is reduced greatly. The effects of simultaneous contrast need to be considered as well.

Those with color vision deficiency (colorblind) will have problems distinguishing about half of the list, and which half depends on the form of the color deficit.


## The Upshot
So in a practical sense, the number of hues that can be discerned ***reliably*** is dependent on the specific design features such as line thickness, and the adjacent colors.

It's not possible to determine the *"number of visually distinct colors"* based on bit depth per pixel. There are too many factors affecting perception. 

And do you consider brown and orange/yellow to be the same hue? Pink and red the same hue? Technically they are, though the color sensation is distinctly different due to the different chroma and luminance levels.

  [1]: https://i.stack.imgur.com/Mn1iE.png
