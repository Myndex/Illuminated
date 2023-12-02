# Nov 22, 2020
[Original](https://github.com/w3c/silver/issues/217#issuecomment-731870954) Note that the below draft conformance model was part of the early Silver experiments, and is here for historical interest.

Hi @spanchang  thank you for commenting.

I am going to respond as to how the conformance model is working right now for Visual Contrast.

**All visible text is in scope**, except purely decorative (i.e. dingbats of flowers in a line). However, the _purpose_ of a given text element sets different limits and requirements, with further variations per level of conformance.

### Brief Overview of Contrasts

In terms of luminance contrast (ignoring size, spatial, hue, and other contrasts) there are four broad categories:

1. Fluent Readability Contrast
2. Contrast for Spot Reading
3. Contrast for non-text objects, images, elements, states (focus), etc.
4. Purely aesthetic Contrasts.

Number 4 has no requirement other than to not interfere with numbers 1 thru 3. Number 1, readability, has by far the highest contrast requirement as needed to enable whole word recognition in the VWFA (Visual Word Form Area) of the brain. Number 2 is a relaxed contrast requirement as spot reading assumes that letter-by-letter lexical processing is acceptable. Number three is a bit more complicated but typically as relaxed as number 2, but in some cases can be more relaxed, yet in other use cases have a higher contrast requirement.

### Use Cases Defined

**(A) Fluent Readability:**
- Columns of body text (body text has elevated requirements for best score)
- Headlines, Subheads, Asides
- Primary navigation, Primary menus
- Descriptive captions that convey meaning beyond the image.
- Font weight and size are interdependent with luminance contrast.

**(B) Spot Reading Level**
- Copyright, ByLine, and Legal Notices and links thereto (secondary navigation).
- Captions that only restate the captioned item or provide only credits, byline, rights, etc.
- Ancillary text that is not a part of, nor critical to the understanding of, the primary content.

**(C) Non-Text Elements**
- This means buttons, controls, form fields, clickable objects but does NOT apply to any text within these items.
- This also includes temporal/spatial state changes (including state changes to text, which is necessarily separated from the text's readability contrast).
- Contrasts within an image or drawing that is part of content.
- Contrasts in size, shape, temporal, and spatial relationships are interdependent with luminance contrast.

**(UX) Aesthetic Contrast**
- Simply anything that is purely decorative, non-readable, not needed for understanding content.
- It can include contrasts that may be helpful for organizing content but are not strictly necessary.
- These have no standard other than to not distract nor interfere with use cases A, B, and C

### Conformance Scoring Levels

**Preferred**
- This is a non-normative "suggested best practices" level. Achieving this achieves Level 4, but does not gain any "bonus" points. It is intended as guidance for more ideal design goals that exceed what is reasonable as a scorable level.
- Includes more restrictive font-size minimums and more restrictive use of low-contrast elements. 

**Score 4 — "Ideal Minimum"**
- The normative minimum for a Score of 4 for the view. 
- Case A elements are very similar to the "Preferred" level, but Case B and C elements have more relaxed requirements.

**Score 3 — "Acceptable Minimum"**
- The normative minimum for a Score of 3 for the view. 
- Case A, B, and C elements are only slightly relaxed relative to level 4.
- Intended as a "catch" level for a well designed and well conforming site that "just misses" in one or two areas of visual contrast performance.
- Also, this level is intended to pass sites that are presently passing 1.4.6 contrast enhanced (WCAG 2.x AAA) provided that the background colors are no darker than #CCC and no Case A content uses a font smaller than 16px.

**Score 2 — "Marginal"**
- The normative minimum for a Score of 2 for the view. 
- Case A, B, and C elements are relaxed relative to level 3. In particular the high-contrast Case A is relaxed, and certain minimum sizes of fonts are relaxed.
- Intended as a way for sites that are presently passing 1.4.3 contrast (WCAG 2.x AA) provided that the background colors are no darker than #BBB and no Case A content uses a font smaller than 14px.

**Score 1 — "Poor"**
- The normative minimum for a Score of 1 for the view. 
- Case A, B, and C elements are relaxed relative to level 2, with few restrictions on minimum sizes for Case B text.
- Intended as a catch-all for sites that are presently passing 1.4.3 contrast (WCAG 2.x AA) despite significant design deficiencies and/or false passes of dark color pairs.
- Score 1 means "deficient" but passing, so that sites can still operate and not be penalized (in places where they are by law to comply) to give them time to address and correct their issues.


### How This Answers Your Comment

The `<header>` or `<footer>` does not denote use cases as defined herein. Nor does the `<main>` or `<article>` or... you name it. 

It is definitely possible (in fact more than likely) that the header will contain text of the page title, and that is definitely a "Case A use case" and the footer could easily have navigational elements that fall under Case A. Meanwhile, `<main>` or `<section>` could easily have Case B and Case C elements.

The point is, that at least for Visual Contrast, use cases do not align with the broader semantic markup of sections and other elements. And definitely NOT header! The closest might be footer, but even then, in the conformance model for Visual Contrast, ALL text is in scope, but there are sub-scope requirements that differ based on use case and score level.

It is the USE CASE that is important, not the semantic markup.

Thank you for posting the comment,

Andy


**_Andrew Somers_**    
_W3 invited Expert    
Myndex Color Science Researcher_

