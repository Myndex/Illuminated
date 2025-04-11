# March 10, 2025
https://github.com/w3c/wcag3/issues/266#issuecomment-2712649837

----
## Canonical Reference

In 2011, Dr. Legge et alia published a review paper "Does Print Size Matter for Reading?"¹, and it's a useful key reference that digests both historical use of type, and modern research. We are fortunate that Dr. Legge has made so much of his work available in open access, I believe this paper can be found at PMC. The cite is in the footnotes.

For the thread, here are a few of the figures & tables that should be instructive.

### Comparing x-heights of three fonts

<img width="600" alt="three fonts compared EDIT from Does Print Size Matter for Reading 2025-03-10" src="https://github.com/user-attachments/assets/77b722c0-45c7-4c16-a9b4-b3da0957d828" />

### Optical scale for fonts
This demonstrates how well designed fonts are intended for a particular size in print. Fonts intended for very small print such as in a footnote, tend to be bolder and have commensurate horizontal spacing, vs a font intended for headlines (i.e. a "display" font).

<img width="600" alt="Optical scale in fonts fro Does Print Size Matter for Reading  2025-03-10 at 6.45.37 PM" src="https://github.com/user-attachments/assets/a34933b3-62d4-489a-a9bf-8325c830d84d" />

### Reading speed vs size
Here, size is the x-height in visual angle (VA). Side note, the peak speed is referred to as "critical print size" by Whittaker/Lovie-Kitchin.
<img width="600" alt="reading speed vs size from Does Print Size Matter for Reading  2025-03-10 at 6.45.02 PM" src="https://github.com/user-attachments/assets/4dd0021d-70ef-47d4-add3-6d471e319530" />

### Common print sizes
A graph and tables showing common used print sizes.
<img width="600" alt="Common print sizes from Does Print Size Matter for Reading  2025-03-10 at 6.46.23 PM" src="https://github.com/user-attachments/assets/a238a157-7b68-4291-8d05-86bdd2b04416" />

<img width="600" alt="Text sizes in books and nespapers from Does Print Size Matter for Reading  2025-03-10 at 6.47.50 PM" src="https://github.com/user-attachments/assets/9abfb65e-a0ea-4a8e-b34c-4fe6ade4fb5c" />

<img width="500" alt="Print headline sizes in newspapers from Does Print Size Matter for Reading  2025-03-10 at 6.48.16 PM" src="https://github.com/user-attachments/assets/9dc6ba00-fb1e-4dbf-b6cf-967304ccc5a4" />


### Font size conversions
A few useful conversions between physical sizes and visual angle, etc.
<img width="859" alt="Font size conversion from Does Print Size Matter for Reading  2025-03-10 at 6.47.23 PM" src="https://github.com/user-attachments/assets/0d84423b-2579-4ee2-8524-727dacde59f8" />

----

**A couple other notes:** the commonly used point `pt` of 72/inch, relates to the CSS reference `px` as `1pt = 1.33px`. `px` is the reference unit for web, and is what browsers resolve to as the `px` is the canonical unit of the CSS canvas. `px` is not device pixels, it is abstracted (in theory, YMMV depending on implementation).

IMO, any web standards referencing absolute units should be primarily using the px, not pt. As an example, in WCAG 2, the `pt` is used, and this has resulted in web designers using the values intended to be `pt`, but with the `px` unit, resulting in font sizes being 25% smaller than that standard demands. (I.e. using 3:1 contrast with an 18px font, when it needs to be 24px, because 24px = 18pt, and WCAG 2's breakpoint is 18pt, not 18px).

Nevertheless, the `pt` unit is used in some environments, such as the iOS app development environment. Therefore, any web/IT standard specifying an absolute size should at least use `px` as primary and `pt` as secondary.




Andrew Somers
_Director of Research_
_Inclusive Reading Technologies, Inc._


¹ Does Print Size Matter for Reading? A Review of Findings from Vision Science and Typography
Gordon E. Legge and Charles A. Bigelow
J Vis. 2011 ; 11(5): . doi:10.1167/11.5.8.
