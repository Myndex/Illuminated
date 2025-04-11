## April 11, 2025
From https://github.com/w3c/wcag3/issues/266#issuecomment-2798129136

regarding a proposed guideline of:    
`Text style: The rendered text does not use a decorative or cursive font face.`

----
> > Text style: The rendered text does not use a decorative or cursive font face.
> 
> _This seems too restrictive a a general rule._

I agree, and it's also subjective, ambiguous, and arbitrary.    
There are many factors that make a font more—or less—readable for users with visual or cognitive needs¹.

# _Leverage Technology not Legislators_
Keeping in mind that these "voluntary guidelines" are now being co-opted by legislators and pressed into law (with the inherent unintended consequences), it's important to separate the _"must have"_ from the _"best practices suggest"_ level of guidance.

_Therefore this guideline is over-broad:_
> **_Text style: The rendered text does not use a decorative or cursive font face._**

Without further qualification, it is at most a best practice suggestion—a _"should"_ and not an _"always must"_. It also presents different implications depending on the language/writing system.

### Importantly, _subjective_ design considerations are not fit for legislative statutes.
A potentially better guideline could be:
- A plain accessible font is provided as a fall back.
- The layout features remain functional when the plain font is enabled/selected by the user.

Or perhaps better, we consider the "prefers" CSS tags, and for the purpose here, develop a new tag along the lines of:
```CSS
@media (prefers-font-family: plain) {
  body,p,ul,ol,li { 
    font-family: irt-plain, verdana, sans-serif !important; 
  }
  h1,h2,h3,h4,h5,h6,blockquote {
    font-family: irt-display, georgia, serif !important; 
  }
  code,pre {
    font-family: irt-mono, "Noto Mono", monospace, monospace !important; 
  }
}
```
Arguably, this organization might consider the advantages of leveraging the technology to accomplish the goals of accessibility, rather than put the full onus on content authors. The web is dynamic content. Dynamic content should be and can be **user preference driven first**, before arbitrary guidelines are made "law" with their unintended consequences.


-----
## Supporting Discussions
### Use Cases of Text
<details><summary><i><b>CLICK HERE</b> to reveal more on Use Cases</i></summary>
.

I would say that columns of **body text**² should most often be in a plain typeface, such as Georgia or Verdana. This is for a number of reasons:

1. Body text is usually the smallest **content text**,³ simpler designs are most often better.
2. Body text is by definition a block, where whitespace and crowding become critical.
3. Body text is usually the content that is most important to be readable at **best speed and comprehension.**

But these factors **do not apply to all text** in a view. Headings or headlines for instance are generally much larger, and serve a different purpose than body text. As size increase, the complexity of a glyph, use of whitespace, and "best speed"  becomes less important (or perhaps best, "differently important"). 

- **Headings** in particular are meant to divide, provide a pause between sections of body text, and well as indicate the upcoming subject.
- **Blockquotes** are often duplicated from the main text, to highlight key points for skimmers,⁴ or advertise some of the substance to encourage deeper reading.
- **Main headlines/titles** are intended to grab attention and identify the article—hence they are large and often of unique design.

.
</details>     

Different use cases mean different user needs/considerations.

### Related Readability Scienceª
The peer-reviewed studies of Lovie-Kitchin et aliaª developed several important concepts directly related to accessibility of text for impaired (and normal) vision.

<details><summary><i><b>CLICK HERE</b> to reveal more on Readability Science</i></summary>
.


- **Critical size:** the size at which further increases do not improve reading speed nor comprehension.
  - While not as sharply defined, there is also an **anti-critical size**, where increasing size causes a reduction in reading speed.
- **Critical contrast:** the text to background contrast for which further increases also provide no improvement.
- **Spot:** above the acuity levels for size or contrast, but less than the critical values, though still readable with fixation.
- **Sub-Fluent:** above spot but less than the critical values, therefore readable though not necessarily at best speed.

Arguably, content body text should meet the critical levels for the needed accommodation. But there are valid—and accessibility related—reasons to clarify that **not everything in a view** must be at or above the critical values.
.
</details>     

### Hierarchical Design
Well designed content has a "flow" or a hierarchical structure that leads the reader through the important content, and prevents distraction or clutter.

<details><summary><i><b>CLICK HERE</b> to reveal more on Hierarchical Design</i></summary>
.


This is an important consideration for all users, and **in particular those with cognitive needs**¹, but certainly visual impairments as well. Consider the difficulty in reading a page that is edge to edge text, all at a high contrast, and with little differentiation. Where does the eye have to land back at the start of a line of text? What is important to look at?

There are many ways to modulate **visual contrast**⁵, and among them are use of whitespace, use of different font designs, and of principal importance the most basic: **font weight or stoke thickness, and text size**.

Finally_**—and among the least important—**_the perceived luminance difference between the text and the background. In particular, once a given critical Lc level is reached, where we venture into contrast constancy, and which depends very much on adaptation to surround, we find that the more important **spatial factors**⁶ (whitespace, weight, size) rule here.
.
</details>     




Thank you for reading,


Andrew Somers
_Director of Research_
_Inclusive Reading Technologies, Inc._
[_**APC Readability Criterion**_](https://www.readtech.org/ARC/#objective-lightness)

----

<details><summary><i><b>CLICK HERE</b> to reveal Footnotes and Bibliography</i></summary>
.


ª [**_Brief Bibliography_**](https://www.readtech.org/ARC/tests/visual-readability-contrast/?tn=resources) of research cited above.    

¹ By **Cognitive needs**, we include ADHD, autism, but also dyslexia, visual stress, and scotopic sensitivity syndrome aka the [controversial Meares/Irlen](https://doi.org/10.1590/0004-282X20190014).    
² **Body text:** content text that is in a block or column, and usually at the smallest critical size.    
³ **Content text:** text that is intended-to-be-read. 
⁴ **Skimmer:** a user that does not read full paragraphs but quickly skims for an overview.    
⁵ **Visual Contrast:** the visually perceivable differences between different design elements, such as text against background, relative sizes, differences in color or lightness.
⁶ **Spatial Factors:** those relating directly to typography, including spacing, stroke thickness (weight), character size, alignment, average characters-per-line, and glyph design.

.
</details>     
