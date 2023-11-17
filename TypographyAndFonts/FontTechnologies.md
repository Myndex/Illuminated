# WCAG3
**Jan 2022**

> _This will need broad research beyond the reference above to better understand what constitutes an accessible type face and how recommendations around type face can be best integated into 3.0. This is a placeholder issue to ensure AG discusses the topic._

This is a principal part of the readability research I am conducting. Glyph design is particularly important—I created a very brief pdf guideline, which is mostly visual examples and comparisons:

[**Evaluating Fonts For Accessibility D.pdf**](https://github.com/w3c/silver/files/7963713/EvaluatingFontsForAccessibilityD.pdf)

Also I know the Readability Group/BBC was doing research in this specific area, the lead was Gareth Ford Williams of Readability Group. Some results of their study in this interesting video: [**dont-believe-the-type**](https://www.deque.com/axe-con/sessions/dont-believe-the-type/)

He has a useful and brief article on the subject as well:       
[**Understanding What Makes a Typeface Accessible**](https://medium.com/the-readability-group/a-guide-to-understanding-what-makes-a-typeface-accessible-and-how-to-make-informed-decisions-9e5c0b9040a0)

The remainder of this post covers some of my notes on user needs, challenges, and needed technologies.

-----
## _Typefaces and Beyond_
Some things to think about, or what do we classify as _part of_ a given font design, and what is otherwise defined by layout. Leading (line height) and kerning/tracking (letter spacing), as well as the capital height and x-height ratios, and particularly weight—all have no standard, and are up to the font designer to determine.

Thus for a given 16px, 400&nbsp;weight font, the actual glyphs are rasterized to screen at a size and weight that is often different compared to some other font even though it's also set at 16px, and this goes for the spacing and other characteristics.

The CSS properties, ` line-height, letter-spacing, font-weight, font-size` etc. are all at the mercy of, and relative to, how those characteristics are designed into the font. It is challenging writing guidelines that involve these important font metrics, as two different font families can vary not only in the design of the individual glyphs, but how they are sized relative to the font body size. Add to that ambiguity of how they are kerned or spaced and the key aspect of stroke width & stroke contrast, and how that relates to a specific weight number like 400 or 700.

Then the subsequent question is that of testability: font design, as in a set of individual glyphs, is complicated and nuanced enough that a reasonable, meaningful, and testable normative standard (i.e. "shall") for all font use cases is essentially out of reach. The critical use case of blocks of body text might be a candidate though.

Keeping in mind that this specific subject has been researched thoroughly for over a century without finding much consensus beyond basics like _"blackletter fonts are hard to read,"_  a reasonable guideline or _recommendation_ (a "should" or "may") is possible, see the appendix for key points.

### _Many Writing Systems_
And here we are talking only about Latin fonts — but there are so many other writing systems in the world (at least 40 common ones serving 6000 living languages IIRC) that have their own unique considerations. As an example, consider that dyslexia is almost unheard of in Korea, as Korean is a clear language. English is decidedly not, and that is the larger, intractable problem.

And on this subject, fonts like "Open Dyslexia" and "Dyslexie" [are not actually useful](https://www.shanahanonliteracy.com/blog/what-about-special-fonts-for-kids-with-dyslexia-or-other-reading-problems#sthash.gmdtuwgs.dpbs), in part as they seem to be based on an assumption that dyslexia is a visual problem — and knowing that dyslexia is language specific, claims it can be solved through special glyphs are unsupported by science.

In one study the researchers found that increasing letter spacing of a common font like Arial had the same benefit as the font Dyslexie which also had increased spacing <sup>[_ref Marinus, Mostard,et.al._](https://onlinelibrary.wiley.com/doi/10.1002/dys.1527)</sup> with the implication that it was not the glyphs, but the crowding which is helped with increased spacing.


## Technology Needed
Because of the lack of consistency in font families, some changes/additions to CSS properties would be helpful for creating actionable guidelines.

### _x height_
The way to make ` font-size: ` consistent in terms of readability is to use the _x-height_ and not the font body height, as is done now. I [proposed last year](https://github.com/w3c/csswg-drafts/issues/6709#issue-1014479467) in the CSSWG a property for setting x-height directly, which is what is needed to accomplish that.

### _spacing_
Along with that would ideally be a way to set line-height based on x-height. 

Letter spacing is trickier since kerning is so tightly entwined with a font's design. Typesetting systems like Quark Express, Illustrator, InDesign allow for optical kerning and additional tools to provide fine-control over letter spacing. That level of complexity is not a part of CSS right now, but would be helpful, but is also processor intensive.

### _font weight_
The problem of inconsistent font weight is non-trivial, and something I am working on. The manual method is [described for APCA](https://github.com/Myndex/SAPC-APCA/discussions/28#discussioncomment-1610289).


-----
## Appendix
### _What Are All the Things_
Specific points of font readability, as briefly as possible, and mainly considering blocks of body text.
- **Size appropriate for acuity of the reader**, meaning the critical size.
    - This is an x-height that is at least two times the measured acuity height in visual angle.
        - I.e. if the smallest capital E that can be distinguished measures 4px, then the x-height of a font needs to be 8px. 
        - If the x-height ratio is 0.5, then that means a 16px font.
    - The aspect ratio is reasonable for the acuity
        - At the minimum critical size, the lower case aspect ratio needs to be less than 1.5:1 (not counting ascenders and descenders.)
        - I.e. an 8px high x that is only 2px wide is unreadable at that size.
    - CSS does not have a useable property to affirmatively and consistently set this as all these attributes vary considerably per font.
- **Appropriate font weight** for the given x-height of the font as used in the design.
    - Very bold, heavy fonts may be hard to read due to self-crowding, and should not be used for small font sizes.
    - Very thin, light fonts need substantial luminance contrast, and be set larger than heavier/bolder fonts.
    - CSS does not have a useable property to affirmatively and consistently set this, as weight is a non-standard attribute that varies considerably per font.
- **Appropriate spacing** (leading and kerning/tracking)
    - General: more spacing lowers spatial frequency, which improves contrast for readability.
        - Less spacing introduces crowding effects and reduces spatial contrasts.
        - Spacing as in padding around a block of text is also important for readability
    - Leading (line spacing): baselines should ideally be 2.5 x-heights apart (or more).
        - For a font like Helvetica Neue (x ratio ~0.5175) this is a line height of 1.3
        - Fonts with a larger x-height need to set a larger line-height, eg. an x ratio of 0.56 needs a line-height of 1.4
    - Tracking (letter spacing): depends on the size, weight, aspect, and glyph design, and the kerning.
        - For instance for a well designed font like Barlow, the letter spacing is 0.08em to 0.16em when including kerning. (8% to 15% of the font size).
        - word spacing about 0.3em to 0.35em (30% to 35% of the font-size).
        - Serif fonts, italics, cursive, etc. tend to need more spacing.
- **Glyph Design** after size/aspect ratio/x ratio, weight, and spacing considerations are established, some key glyph considerations are:
    - Good counters (the hole in lower case e for instance — it should be large enough to be distinct.
    - Adequate ascenders and descenders, such as for the d b p q h y g, should be distinct, a minimum of 33% of the x-height, or more.
    - 1lI Distinct numeral ` 1 `, lowercase ` l ` and upper case ` I `
        - GOOD: the code font` 1lI - but MEH: the normal font` 1lI
    - rn m Distinct ` rn m ` so when r n are  together, they are not mistaken for m
    - No mirrors: db should be unique and not just mirror copies, same for qp
    - Descender distinction: q g y j  ` qgyj `

EXAMPLE _Does the meaning change:_
    - ` I saw Haley's Comet ` or 1 saw HaIcy's Cornet
    - I saw Haley's Comet or ` 1 saw HaIcy's Cornet `

- Special, ornate, cursive, or flourished font designs
    - Should never be body text
    - Do have their place in some designs, but the impact on readability needs to be recognized.
        - For instance, important information first displayed in a highly ornate font should be shown again in a more normal font.
**Example:** very ornate flourished words : _"You're Invited to our Wedding June 1st at 3pm"_, at the very least _"June 1st at 3pm"_ needs to be repeated in clear text elsewhere on the invitation.

- **_Tangential to the font design and built-in metrics:_**
    - Device resolution makes a difference.
        - On lower resolution devices, sans-serif font usually work best. 
        - On high-res (retina), serif fonts work as well as print.
    - The combination of font-weight and font size determines the needed lightness distance for adequate readability contrast.
       - For very light weight fonts with thin strokes such as weight 100, even maximum color contrast may not be enough if the size is also small.


## The TL;DR
- Research shows that readability is substantially affected by:
    - metrics like letter/line spacing
    - glyph weight, which directly affects visual contrast
    - Size, especially the x-height, for a user's acuity needs.
        - Size is also the single readily available feature for user change (zoom).
    - While it is true that some glyph designs are more readable that others, there is a general lack of consensus on absolute specifics.



Thank you for reading,

Andy


_Andrew Somers_     
_Senior Title & VFX Supervisor_      
[_General Titles & Visual Effects_  ](https://generaltitles.com)    
