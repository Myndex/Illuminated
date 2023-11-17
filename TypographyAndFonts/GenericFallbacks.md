## Generic Font Fallbacks for Accessibility and More

Hello everyone, I'm going to start with a response to something Chris @svgeesus mentioned above:

> _Do generics make sense in a world where downloadable fonts are the norm and generics merely influence fallback?...SNIP... I feel that we can't reasonably define the existing generics or indeed extend them, without clarity on their purpose._

While downloadable fonts were a boon to designers, downloadable fonts are also responsible for many of the problems of visual accessibility of web content today. As you know I am immersed in researching solutions for these problems.

In thinking about this topic, it is an opportunity to address font related accessibility issues. I do think it would be good to specify some very standard fallbacks, but those fallback fonts should be ones that are also accessible. This provides a utility of purpose and defined need for defining and extending the existing generic font types.

At the moment, the common generics _"Arial"_ and _"Times New Roman"_ are not accessible-friendly. If we look at the old "MS core web fonts", the two most accessible are those designed by Matthew Carter, _"Verdana"_ and _"Georgia"_. Even so, some tweaks could be added to a few glyphs with a eye to improve accessibility. 

I'm not certain the license situation on those two, not just regarding redistribution but also for creating derived forms for extended language sets and for adding accessibility attributes. Nevertheless, Ideally the generics would be actual, specific fonts to improve cross platform compatibility.

There are however a number of open-source fonts where we could modify as needed for accessible versions to be the generic fallbacks for when a specified font is not available. Of course this raises questions regarding other languages. 

-----
## Reasons and Categories
But some good reasons for defining a specific font family for each generic name/type:
- Accessibly fallback
- A reference font for accessible standards such as WCAG 3 Visual Contrast for fonts.
- A design fallback when the specified font is unavailable, a common occurrence.

If those are the reasons, and we want to help content creators maintain some consistency while achieving these goals, then I'd suggest the following as a starting group of font classifications.

### _Basic Font Set_
A useful minimum set of generic fonts.

**_Content and Body Text_**
- **serif** — _Libre Baskerville_ is an ideal example of an open source accessible serif font. Serif fonts normally have contrasting stroke widths central to their design.
- **slab-serif** — Slab-serif fonts are distinctly different from serif, not only due to the squared off nature of the serifs, but these fonts also have little to no stroke width variation.
- **sans-serif** — No serifs of course, and usually a fairly consistent stroke width. Though for accessible reasons, some glyphs like the lower case l or capital I should have something for distinction, the way Verdana handled the capital I. 
- **trans-serif** — Trans-serif is a sans-serif font that otherwise has contrasting stroke widths such as _Optima_. Another good example of this style is _Artifika_.

**_For Display/Headlines/Spot Reading Elements only:_**
- **sans-cond** — condensed or narrow fonts are generally bad for body text and most readable content when under 32px, but a font like Oswald or Barlow Condensed has a place as a headline font.
- **sm-cap**, sans-sm-cap, slab-sm-cap, trans-sm-cap — as above, bad for body text, but small-cap variants do make useful headline/display fonts, and real small caps are not the same as the synthetic "just make it smaller" as the weight is balanced in a real small cap font.

**_Monospaced_**
- **mono-pre** — A serif monospaced font like the **_real_** Courier (but not Courier New...)
- **mono-code** — a sans-serif monospaced font like Source Code Pro, Menlo, or Fira Code. These are preferred as they have regular, bold, and oblique versions.

**_Special_**
- **symbol** — traditional dingbats.
- **icon** — Not dingbats, but icons like a home, envelope, gear, hamburger.
- **math-basic** — This is important, so to echo @fred-wang 's comment on the importance of a generic math font for mathML, is there a benefit to a more complete math font,
- **math-full** — a more complete math font such as used with one of the LaTeX math libraries?

**_Bonus, the "Non-Accessible" styles people like to use:_**

Some of these might have use for headlines, but shouldn't be used for body text that is meant to actually be read. But then should fonts like "fantasy" be a part of the generic font set at all? Once we get into this subgroup of fonts, generic fallbacks become less useful, whereas the generics above are all very useful.
- **swash** — More consistent with the serif generic font than "fantasy".
- **handletter** — Hopefully not comic sans. Courgette might be a fit.
- **blackletter** — Also not very accessible. I created a blackletter font with modernized glyphs a few years ago named "Legible Olde English" which was more readable, but I still wouldn't call it accessible by any means.
- **cursive** — hard to think of a "cursive" font that is also accessible. Snell Roundhand is pretty... pretty unreadable that is... I suppose Lobster Two might fit for accessibility _"it's not horrible"._ But Lobster is also a very opinionated, narrow "look" to be used sparingly. And thus, should there even be a generic? 
- **fantasy** — At the moment this could be called "font roulette", and as a descriptor is somewhat meaningless isn't it? Again, should this even be a generic?

-----

## Regarding Accessible Fonts
On this point, I am not talking about fonts as far as their aesthetic design. I am talking strictly about _accessibility_, including research on dyslexia, cognitive, contrast perception, and visual impairments. 

### _Some accessibility points are: does a given font..._
- have adequate tracking, kerning, and leading? _(letter spacing and linespacing)_
- have an adequate x-height? _(Ideally ~60% of the font-size)_
- have adequate weight? _(Adequate stroke thickness at 400)_
- have a "good" Cap-height? _(For differentiating from x and allowing good leading)_
- avoid common homoglyphs? _(Meaning_ **rn** _vs_ **m** and **1** _vs_ **l** _vs_ **I** _are distinct.)_
- avoid mirror image glyphs? _(Meaning_ **db** or **qp** or **MW** _are not literal mirror copies)_
- have good hinting for screen use? _(Meaning is designed to render well to standard resolution screens.)_

Most of these characteristics are discussed prominently in the current research into readability. For cites, I refer to Lovie-Kitchin, Bailey, Arditi, Legge all of whom have done the bulk of the work in readability research for normal and impaired vision. 

### ...to the core
If we consider the "MS core web fonts" which MS distributed once upon a time, namely the proprietary fonts _Andalé Mono, Arial, Arial Black, Comic Sans MS, Courier New, Georgia, Impact, Times New Roman, Trebuchet MS, Verdana_ and _Webdings,_

Of _THAT_ group, only _Georgia_ and _Verdana_ are really accessible friendly, and perhaps Andale Mono with reservations. But what about _Trebuchet ?_ The problem with Trebuchet is the default track/kerning is too tight, so it's not normally on my list of "good" fonts for accessibility.

Also of that group, _Courier New_ is nothing short of an **_unusable illegitimate version of the classic Courier typeface._** _Arial_ is nothing but a pure copy of _Helvetica_, which I also give somewhat low marks to regarding _accessibility_. _Times New Roman_ with its small size and small x-height make it less than desirable for web use (The small size of Times made it a choice for newspapers who were concerned with jamming as much text into as small a space as possible).

On this point, there is another pressing issue in terms of web content and that is the very non-standard nature of font metrics. Font size and font weight are not consistent to the point of being irrelevant across different families, even within the same foundry.

### _Examples:_

<img width="681" alt="Font Size Compared" src="https://user-images.githubusercontent.com/42009457/135391183-02ca89fc-aed7-4288-9222-3da01fa3e098.png">

_Real_ Courier is a fairly readable font, but the MS commissioned _Courier New_ is so very light it is unusable.

Times New Roman renders smaller than many other fonts for a given font-size. While newspapers try to save paper, this is an accessibility problem and there is no "paper" to save on the web. 

I do have proposal I am preparing to address parts of the size problem, which I'll post soon.

Also for the record, my critique on some fonts is only and exclusively directed at accessibility issues of the cited fonts.

I have a [brief informal review of accessibility in fonts ](https://www.researchgate.net/publication/338149302_Evaluating_Fonts_Font_Family_Selection_for_Accessibility_Display_Readability) with many examples and some discussion that is related to this issue.

-----
## TL;DR

- I believe we should have defined generics that also serve as fallbacks for accessibility.

- These generic fallbacks would also serve as the "reference" fonts for WCAG guidelines for defining example size and weight characteristics.

- These generic fallbacks would also provide a useful substitute when a user agent was unable to load a specified font. This is a common enough occurrence that should not be overlooked in terms of a reliable need for generics.

Thank you,

Andy
