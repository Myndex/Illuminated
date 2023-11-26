# Nov 26, 2023
Response to DJ Chase @u9000-Nine
Note: my "drinking from a firehose prolixity" is part of my process in working through ideas. I've hidden most of the backwork under "Click for details".

----
# _Weight is spatial_
> ### _Visual text attributes (better name needed) distinctions_
> * _Font-weight_

IMO font Weight is the primary, most critical "spatial quality" because it directly defines the _spatial frequency_ which directly affects contrast sensitivity, which ultimately determines the perception of contrast, and with that, readability.

_Click to enlarge:_
<img alt="New contrast sensitivity Graph 5 new leads NOT APCA all same" width="240" src="https://github.com/w3c/wcag3/assets/42009457/da0700ba-3c03-423b-954c-77a424c75a36">     
In the graph above, all the sample text is in the same color, but the different weights indicating the approximate placement on the human contrast sensitivity curve for a practical demonstration of the abstract science.

Most other font attributes are also spatial in nature, at least in part, but not always as critical to that definition.


## User Needs Summary
If we think about this from the user-need perspective, the four related core user needs for text/readability/structure accommodations are:

- **Visual Acuity** (size)
- **Contrast Sensitivity** (weight & color)
- **Color Insensitivity "colorblind"** (N/A _except_ no "reds on black")
- **Cognitive & Lexical** (all three above, plus use-cases, hierarchy, and more)


<details>
<summary><a id="this" href="#this"><b>CLICK</b></a> (open/close)</a> <i>Detailed User Needs Summary</i></summary>
⇩ ⇩ ⇩ ⇩ ⇩


### Acuity Impairments
- **Visual Acuity** _(directly impacted or assisted by font size)_
    - The **critical font size is 2x to 2.5x the _acuity_ size** for a given user, provided it is at or above the critical contrast level.
    - The desired outcome is that users can set the smallest content font to their individual critical size, and that larger fonts maintain a larger appearance but do not get "too big", as fonts too large negatively impact readability.

### Contrast Impairments
- **Contrast Sensitivity** _(directly impacted by contrast determining features)_
    - Font **weight**, and non-text line **thickness**, are the **primary** determining factors for **perceived contrast** for strokes less than about 4px thick.
    - The **critical font weight** is directly **interrelated** with the **critical lightness contrast**.
    - The critical contrast _reserve_ depends on the intended **use-case** and desired readability level of the text (best fluent, high fluent, sub-fluent, non-fluent (spot).)
    - The preferred contrast reserve, such as for article body text, is **20 times** the JND **threshold** for the given user.
    - Lower levels such as 10x for fluent, 6x for sub-fluent, and 3x for non-fluent (spot) are also detailed in the corpus of research (Lovie-Kitchin et alia).
    - Font size **only applies** to contrast to the degree it **affects the rendered font weight/stroke thickness**.
    - White space, including letters and line spacing, directly affects contrast perception.


### Color Impairments
- **Color Insensitivity (colorblind)** _(minimal reading impact, other than **red on black**)_
    - The one lightness contrast concern is saturated colors with substantial red. 
    - Reds should always be the darkest of a color pair.
    - I.e. saturated reds, oranges, or purples should generally not be paired with black or dark.
    - The reds on black prohibition is especially critical for those with protanopia and achromatopsia.
        - That said, the **low luminance** of saturated reds makes the red on black restriction the **_preferred practice for all users_**.
    - Also no saturated deep blues on black (for **all** users, regardless).
    - The _actually color blind_ achromatopes also need **AT** due to co-morbid low vision and photophobia.

### Coga and Language
- Cognitive & Lexical _(directly impacted by layout/visual hierarchy, use of colors, and more)_
    - The visual hierarchy guides the user through the intended content, using visual contrasts.
        - font weight (and line thicknesses) primary contrast impact
        - white space for grouping (padding, paragraph & heading spacing)
            - Also direct impact on visual contrasts.
        - font size, font family, style 
            - Tangential effect on contrast due to how these affect rendered weight.
        - white space for contrast (letter, word, & line spacing)
        - use of lightness contrast to aide the visual hierarchy
            - secondary to maintaining readability for the use-case
        - color (hue/saturation) to aide the visual flow/grouping
    - Use of color (hue/saturation) and text decoration
        - some users need muted, non-distracting colors overall
        - some users need brighter, vibrant colors for a task
        - multiple schemes available to user; automated schemes
    - Containers 
        - size relative to viewport size
        - scroll inhibition
        - text reflow
        - functionality preservation
    - Use of motion, state indication, non-motion animation, haptics, other feedback mechanisms.
        - Persistent user preferences, especially when 
    - Interactive elements 
        - use of color or marking with decoration (such as underlines)
        - grouping by use, kind, purpose, etc.
        - inline links consider trade-offs for readability vs link identification
        - use-cases for priorities: block text readability is critical, in a reference block or nav, links are more critical.
    
 ⇧ ⇧ ⇧ ⇧ ⇧     
_END Detailed User Needs Summary_

</details>

-----

<details>
<summary><a id="this2" href="#this2"><b>CLICK</b></a> (open/close) <i>Connect User Needs to Design Elements</i></summary>
⇩ ⇩ ⇩ ⇩ ⇩

For the four core readability needs, _acuity, contrast, color, coga,_ we find that:

1. **Font-weight:** primary **_spatial_** contributor to visual contrast.
2. **Lightness contrast (achromatic luminance):** primary **_non spatial_** contributor to visual contrast.
3. **Font-size, -family, -style:** these properties are more spatial than not.
    a) _BUT_ for the most part they contribute to visual contrast only **to the degree** that these properties **affect the final rasterized stroke weight**.
    b) these properties are effective tools for the structure of the visual hierarchy.
4. **White space:** Spatial, affects cognitive needs a bit more than visual contrast.
    a) adequate padding helps contrast and helps grouping for the visual hierarchy.
    b) adequate letter and line spacing helps contrast and helps readability
    c) user preference to increase letter/line spacing can help dyslexia.
5. **Color (Hue/Sat):** color is functional at the lowest spatial frequencies.
    a) color is _NOT_ a contributor to _readability_ contrast
    b) improper use of color can result in blocking conditions for some users
    c) color can cause blocking of readability in certain edge cases.
    d) color can be very helpful for visual hierarchy, grouping, and other cognitive needs.
    e) but color should not be the only way to arrange and define the visual structure, nor convey information.
### Color should _expand_ not _explain_

- Acuity - #3a with modest help from #1 & #2 (maintain critical contrast)
- Contrast - #1, #2, #4ab, with help from #3a (font metrics that contribute to contrast)
- Colorblind - #5bce (Some algorithms help #5bc by adding protan compensation)
- Coga - #4abc #5bcde with help from #1, #2, #3b

 ⇧ ⇧ ⇧ ⇧ ⇧     
_END Connect User Needs to Design Elements_

</details>

-----


### Distinguishing Texts in the Hierarchy
Taking another stab at this, I'd class weight/stroke width and all whitespace as _spatial_. For font-size, there are arguments for spatial or font characteristics. Because font-size is (should be) universally **adjustable by the user**, setting size under font layout makes sense, particularly considering reflow.


## Content Structure Groups
For Headings, Body-Blocks, Nav, Main Content (proposed)

* **Spatial** — _Contrast_
* **Font** - _Layout_
* **Content** - _Language-based Structures_
* **Non-text** - _Decoration/Indication_


### Spatial - Contrast
 * Font-weight (as rasterized)
 * Luminance or Lightness Contrast
 * White Space
     * Alignment and justification (Left, center)
     * Outdent, indent, flush to body (left for LTR)
     * Leading (line space) before > after
     * Tracking & kerning (letter spacing)
 
### Font - Layout
 * Font-size _(always user adjustable)_
 * Font-style (upright, italic, Oblique, infant, etcetera)
 * Font-family variants:
     * serif, sans serif, trans serif, slab serif, mono-spaced serif, mono-spaced sans-serif, display, hand, script, decorative, swash, ornamental, fantasy, cursive
     * For bicameral scripts: Mixed case, small caps, all caps, all lower¹
     * aspect ratio (condensed, expanded, etcetera)
* Writing direction, text orientation.²
* Text-decoration (underline, strikethrough, drop shadow, etcetera)³
 
### Content - Language-based Structures
* Capitalization style: for headings, titles, nav, etcetera
    * Consistent style per language (Chicago, APA, AP, etc.)
* Writing system/direction: Mixed/alt scripts if supported²
* Perspective: first, second, limited third, omniscient third
* Voice: active, passive
* Tense: present, past, future
    * _simple/continuous/perfect/perfect continuous_
 
### Non-text - Decoration/Indication
* Text-decoration (underline, strikethrough, drop shadow, etcetera)³
* Horizontal or vertical rules
* Borders or outline (includes focus visible)
* highlighting or local background adjust
* Iconographic or textual indicators (§ ¶ • – » › > ➣ 💡 ✅ 🔹 [link icon])


I think it's best to group by 
- **use-case ➣ content purpose ➣ psychophysical process**. 

For instance, luminance is achromatic (disregards hue) and is processed by the human vision system _separately_ from color (hue/saturation). Luminance (lightness) serves different functions from color (hue/sat) including cognitive, language, object recognition, motion, etc. 

<details>
<summary><a id="this3" href="#this3"><b>CLICK</b></a> (open/close)</a> <i>Grouping by Process/Function</i></summary>
⇩ ⇩ ⇩ ⇩ ⇩

## Stimulus Processing and Impairments


It is reasonable to divide design aspects according to how processed, and their role in cognition, etc. 

- **Luminance** related
    - lightness/darkness/brightness perceptions are processed from luminance
    - luminance has our highest spatial resolution, but is weak for tasks of differentiation, with a single axis from dark to light.
        - i.e. it's hard to tell one gray from another unless they are adjacent.
    - luminance holds all the fine _spatial_ details, i.e. edge detection, textures, contrasts.
    - luminance holds text: letters ➣ visual word form area ➣ language processing

- **Color** (hue saturation) related  
    - Standard vision detects four unique colors (red yellow green blue), and all other colors are perceptions processed from these.
    - Color has very low resolution (spatially) less than a third to a fifth of luminance, but standard color vision excels in differentiation with two axes, a red/green and a yellow/blue. 
    - Color holds most of the differentiating information (ripe vs unripe oranges) and is used in onject recognition and motion, but is _not_ usually part of language processing, nor fine details.

### Key impairments

- Acuity deficit impairs fine details and luminance resolution due to "out of focus".
    - Making text _larger_ helps bring them to a point they can be focused.
- Contrast deficit impairs the ability to distinguish lightness changes, like edges or faint details.
    - Making text bolder, or making the lightness contrast higher helps.
- Color deficit impairs the ability to distinguish between colorful objects.
    - Ensuring that other identifiers are used to indicate the information presented in color is what helps here.
- Cognitive and neurological deficits impairs the ability to break down and understand structures or meaning from content, or to navigate content, or to be distracted by chaotic or "busy" content, or to become overwhelmed by complicated tasks with content, or to read content clearly (i.e. dyslexia).
    - Ensuring that content follows a clear hierarchy, and that the user has adjustable personalizations for properties such as letter spacing, is among the ways to help here.

### _Summary of this post's concepts_
1) Standard color vision has three axes total for decoding light and color (one luminance and two color)
2) Color insensitivities can reduce this to two (one luminance and one color axis) 
    - or even a single axis (luminance only) in rare cases.
    - Some of these reductions include a significant loss of visible red.
3) Acuity and contrast deficits impact the ability to focus on or see detailed information.
4) Cognitive & neurological impairments can be triggered or confused or overwhelmed by content that is disorganized, busy, chaotically colorful, lacking color, overstimulating, under-stimulating, etc. 
    - Clear hierarchies, using color to _augment_ organizational structures, providing alternate schemes and layouts a user can select, are helpful here.

 ⇧ ⇧ ⇧ ⇧ ⇧     
_END Grouping by Process/Function_

</details>

-----

_Footnotes to "Font - Layout"_     
<sub>¹ Small caps and all caps are only for mixed case (bicameral scripts), and probably fits better under content. </sub>    
<sub>² Writing system and text orientation could fit under font or content, possibly better with content. </sub>    
<sub>³ Text decoration, such as underline, fits best under non-text, which is also probably best for link indication, but other decoration such as text-shadow or outline-text is probably better as part of font characteristics. </sub>

