# March 9, 2025
https://github.com/w3c/wcag3/issues/266#issuecomment-2708801429

----
Comments on the exploratory doc and also font sizing.

## The Canonical Size Reference
The useful touchstone is the CSS canvas, and the **CSS reference px**. The px is defined in terms of visual angle. This sets a reasonable point for the author, as it is **device independent**. One CSS px is 0.0213 degrees or 1.278 minutes of arc. 

<details><summary><b>Click Here for More on Reference Size and Infographics</b></summary>
.

Device makers themselves determine how the CSS px will resolve on their screen, at a given expected use distance. It should be noted however, that device manufacturers do not necessarily adhere to the 1.278 minutes of arc premise, and also, the actual distance from the user can be quite variable.

Importantly: lower resolution (i.e. standard 72 ppi) displays may be assumed to be used at a greater distance, while modern retina-type displays, with their higher resolution may be used closer. But as designers and standards authors, consideration needs to be given to the lowest denominator.

All of this to ask if the 0.0213 degrees or 1.278 arc minutes should be revised?


<img width="600" alt="Image" src="https://github.com/user-attachments/assets/0dafdb8c-5637-486e-a5e9-834019d7448b" />

...

</details>

## Acuity Size vs Critical Readability Size

20/20 vision¹ (6/6 in EU) was defined by Snellen as being able to resolve a capital E that is 5 arc minutes tall, and where the stroke is 1 arc minute thick. 

Internationally, the **median vision is 20/40**, which means that the letter needs to be twice the size to resolve, implying the target E is 10 arc minutes high, with a stroke width of 2 arc minutes.

Importantly, that "E" relates to minimum resolving, but NOT best readability. **Best readability is 2 times larger and at or above the contrast constancy point.** Whittaker/Lovie-Kitchin refer to this as acuity reserve.² We also know that for standard vision, the range of best fluent reading is from 0.2° to 2.0° of visual angle.³ 

When discussing a mixed case language like English, where the lower case makes up the bulk of the long-form texts, then the measurements for font size needs to be anchored to the lower-case letter forms (glyphs). For english, we typically use "x-height", the height of the lower case x. For 20/20 vision, the theoretical "critical" readability height⁴ is an x-height 10 arc minutes high, or about 8px. For a typical font (Helvetica) with a 0.52 x-height ratio, that's a 15px font. This is assuming the 2:1 acuity reserve, and the subject's acuity is exactly 20/20 per Snellen. 

Legge et alia indicate the acuity reserve may need to be more on the order of 2.4:1, per the studies that indicate a critical size at 0.2°, which is 12 arc minutes. Here's a small chart that demonstrates various levels of acuity reserve:

<img width="680" alt="Image" src="https://github.com/user-attachments/assets/b5bf8449-c459-4fb7-b7cc-65b201296713" />

- Definitions:
  - Spot: text that only needs to be readable with fixation
  - SubFluent: text that is not important to understanding the content, and should also be non-intrusive, or a secondary part of the visual hierarchy.
  - Fluent: Most readable text that is part of content in some way.
  - Body: Text that is set in blocks or columns, and should be at the highest readability.

### x-height ratio
Because x-height is critical, it is important to know the ratio of x-height to font size. Some fonts such as Verdana, which was designed for screen use, have a large x-height, with a 0.55 ratio. Other common fonts such as Arial or Helvetica have a 0.52 ratio. Meanwhile Times New Roman has a very small 0.45 ratio. Per the chart you can see that for the same critical size, the actual font size varies wildly do to the different x-height ratios.

The important conclusion here is that specifying font size is not instructive for english language fonts. Or if a font-size is specified, the x-height ratio must also be stated.


### Zoom Implications
Per the chart above, we can see that a 200% size font only gets us to accommodating 20/40. IMO accommodating through most of low vision should be the goal, and that implies that body text can be increased to a 400% zoom. Beyond that and there are diminishing returns as reading speed slows down with very large text (exceeding 2°).

<details><summary><b>Click Here for More on zooming</b></summary>
.

But in reality, a percentage increase is not the goal—the goal should reasonably be enlarging the smallest text up to a certain size, and larger texts being increased but by a smaller amount.

Moreover: what is specifically needed is **_"following user's device settings for font size"_**. Modern devices and OSes have ample settings for accessibility—but in too many cases, apps and content do not follow those settings, or those settings break content.

Due to my low vision, I need text fairly large, but setting it large at the OS level causes much content to break, as in, text reflows to become hidden, or cut off, or clickable areas no longer function. This is especially a problem when I zoom up a page only to find I cn no longer click on the interactive elements.
...

</details>


### Justification
Left to right reading text, when the text is dynamic and reflow-able, should generally be left-justified (left aligned). 

Full justification (left and right aligned) is really only permissible for **fixed text**, and center justification should be allowed for small clips of up to three lines.

<details><summary><b>Click Here for More on justification</b></summary>
.

Full justification (left and right aligned) is really only permissible for **fixed text** that has been typeset, and that can not reflow (i.e. a PDF or other static document). A reason is that to properly do full justification requires a skilled typesetter. The dynamic type-layout features in a browser are weak in terms of advanced tracking/spacing etc, and full justification does not work well for typical web dynamic text.

Center justification should be permitted for short clips of up to two or perhaps three lines max. Center justification is fine a two line headline for instance.

Center justification is also needed in tables, and some forms of data display, so simply prohibiting center justification is also not ideal. 
...

</details>


## Regarding Languages
In the list of a few languages, I noticed Chinese, but not Japanese. 

If only one asian language was going to be listed, Japanese is possibly the most ideal. The reason is Japanese writing commonly consists of both logographic Kanji, and also syllabic Kana. There is some research underway in Japan regarding this writing system and perceptual contrast methods.


<details><summary><b>Click Here for More on languages</b></summary>
.

For a given font size, logographic Kanji is more complicated and tends to have much thinner stokes, and is very similar to Chinese. Syllabic Kana, being more of an alphabet, is less complicated per glyph, and tends to have thicker strokes. Japanese writing combines both Kanji and Kana on the same page/same line. 

Keeping in mind that contrast is first dependent on spatial characteristics (size and line thickness) this brings a layer of complication regarding text appearance with Japanese writing.

The Korean language is unique, in that the symbols combine into blocks, and not linearly. While it's not a widely used language, it is interesting in that "dyslexia" is nearly unheard of In Korea, as the language and writing system is clear/phonetic (unlike English).

Other writing systems: Greek? Hebrew? Math and math symbols? Pictographs and dingbats? And guidance on alternate unicode glyphs are important to consider at some point.

...

</details>


Thank you for reading


Andrew Somers
_Director of Research_
_Inclusive Reading Technologies, Inc._




¹ 20/20 is not perfect vision (perfect normal vision is about 20/12). 20/20 was chosen largely for mathematical convenience (Snellen).
² Whittaker SG, Lovie-Kitchin JE. Visual requirements for reading. Optom Vis Sci 1993; 70: 54-65.
³ See G. Legge's book, "Psychophysics of Reading" and also "Does print size matter for reading?
A review of findings from vision science and typography" G.Legge, C.Bigelow • Journal of Vision (2011) 11(5):8, 1–22
⁴ Also referred to as _Critical Print Size_, or CPS. this means the minimum size at the given contrast for maximum speed, beyond which there is no additional gain in speed.
