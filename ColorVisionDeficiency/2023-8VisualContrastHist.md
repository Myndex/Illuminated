# Aug 10 2023

Hi @bruce-usab @GreggVan 


Bruce:
> > _The intent of this Success Criterion is to provide enough luminance contrast between text and its background, so that it can be read by people with moderately low vision or impaired contrast perception, without the use of contrast-enhancing assistive technology._

Hi Bruce, I think this is good, and I like it better here without the parenthetical.


Gregg:
> _This is not quite correct. When these were created the contest was calculated to account for BOTH low vision and color blindness together in a person.  (We did the calculations)_ 

Hi Gregg, one of the tasks we examined in the Visual Contrast group was to understand the ideas and motivation behind the original SC from 2007. I discuss some of that [in thread 1705](https://github.com/w3c/wcag/issues/1705#issuecomment-1027058976).

The last ten years of vision science, and particularly impairments, has expanded understanding. With the current understanding:

1) **VA+CS:** It's not ideal to conflate visual acuity and contrast sensitivity, as there is not a consistent relationship.¹ VA and CS are separate, largely independent visual functions.

2) **Color vision deficiency**, especially deutan and protan, have as good or better luminance contrast sensitivity and visual function overall, compared to standard vision²⁻³. One theory behind this as regards to dichromats, is due to a lower neural noise.

As I've written about⁴, protans experience the one readability-related luminance contrast deficit in the edge case of red-based colors when paired against black, as protanopia sees the sRGB red primary as about 55% darker. As a result, saturated reds, oranges, and purples are generally best paired with white and not black (other impairments notwithstanding).

Readability is about luminance contrast, disregarding color (hue/chroma), as high spatial frequencies, i.e. text, are a function of the luminance channel in the HVS. Hue/Chroma processing is at very low spatial resolution.

An expanding understanding here also, is how correcting for one visual impairment may be detrimental to other visual impairments, pointing to personalization as the ideal solution.

Thank you for reading.


_**References:**_
1) [Relationship Between Acuity and Contrast Sensitivity](https://iovs.arvojournals.org/article.aspx?articleid=2770151): Differences Due to Eye Disease (Low Vision|June 2020)
2) [luminance contrast sensitivity in color-deficient observers](https://pubmed.ncbi.nlm.nih.gov/24103453/) Márta Janáky et al., 2013
3) [Contrast sensitivity of patients with color vision deficiency](https://link.springer.com/article/10.1007/s10792-018-0881-7)) Cagri Ilhan et al., 2018
4) [What’s Red & Black & Not Read All Over?](https://tangledweb.xyz/whats-red-black-also-not-read-573b9c0a97ed) Somers, Jan 2022
