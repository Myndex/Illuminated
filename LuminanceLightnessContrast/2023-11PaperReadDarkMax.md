# Regarding slightly off white
**Nov 4 2023**

Yes, for main content, though there are issues worth discussing for both light and dark mode.

## Light mode first

With a bright background, `#ffffff` can promote eye blistering fatigue, depending on how bright the display is relative to the eye's adaptation state. Considering that many modern devices easily exceed 1000 nits, visual fatigue is an ever-present problem.

One aspect of fatigue results from viewing high luminance relative to adaptation. If it is caused by a greater bleaching of cone opsins than can be replenished, aka the snow blind effect (this is not actual photokeratitis which is exposure to excess UV, but a loss in sensitivity due to high luminance), or from [blue or HEV light](https://www.optometrists.org/general-practice-optometry/guide-to-eye-exams/why-are-annual-eye-exams-important/blue-light-and-screens/computer-eye-strain-from-high-energy-light/#:~:text=Our%20eyes%20absorb%20all%20kinds%20of%20light%2C%20including,your%20computer%20can%20also%20contribute%20to%20eye%20strain.), is a subject of continuing study.

There are some rather unfortunately misunderstandings floating around the internet suggesting that text be light grey, or that you don't want "too much contrast". Most of these ideas are bunk. One in particular seems to be sourced from an 2018 article at UXMovement, which is a source of much false or misleading information.

In light mode, text should ideally be black. Feelings of "too much contrast" are due to too much luminance. This problem led to the following:


### The Paper Reading Experience
Something we've been working on, The Paper Reading Experience, is a design guideline for light mode, intended to emulate the nature of reading black ink on diffuse white paper, but presented on a self-illuminated display.

The problem with just using an off white like `#eeeeee` is that `#eeeeee` will simply become the peak adaptation level within a minute or two, and therefore no different than `#ffffff`.

_Click for full size_
<img alt="Adaptation demo" width="180" src="https://github.com/w3c/csswg-drafts/assets/42009457/a7959f07-b504-43a2-b725-159ccae975ea">

So, to make an "off white" background useful, there needs to be a full white `#ffffff` in the peripheral vision in order to anchor the adaptation state to the peak white of the display.

The [APC-Readability Criterion](https://readtech.org/ARC/) site uses this technique. (note this is a draft, and the responsive aspect of the site is a little buggy on cell phones.)

Background: 80%  Edge: 100%     
<img alt="Paper Reading Experience" width="703" src="https://github.com/w3c/csswg-drafts/assets/42009457/92538695-e33d-4ca3-b0d8-9361ceda1149">



### Earlier Experiments still up
- [A directory page](https://www.myndex.com/WEB/Perception)
- [Color Blind Simulator](https://www.myndex.com/CVD/)
- [This article on SEO](https://www.myndex.com/WEB/RedirectsForSEO)
- [Article on Luminance](https://www.myndex.com/WEB/LuminanceContrast).

Comments are welcome at [Paper Reading Experience Discussion](https://github.com/orgs/A11yReadTech/discussions/8)


## Dark Mode

Unlike light mode, there _is_ a level of "too much contrast" in dark mode because of the darker adaptation resulting in wider pupils, and the nature of glare, scatter particularly of point sources, and especially for those with astigmatism. Halation is more problematic in dark mode than in light mode.

We are evaluating a max contrast for dark mode, testing $L^c\ -90$ for text smaller than 24px, and $L^c\ -85$ for larger/bolder text. Thread to [discuss maximum contrast.](https://github.com/Myndex/SAPC-APCA/discussions/106)

How dark should the background be in dark mode? IMO that is relative to the surrounding environment. At night, in a dark environment, a full black BG could be fine, provided the text is also dimmer. For a `#000000` BG, text is ideally between `#cccccc` and `#e4e4e4`.

A lighter dark mode BG such as `#444444` and `#f4f4f4` might be preferred by some for a lighter environment.

Examples:

![DARK MODE light surround](https://github.com/w3c/csswg-drafts/assets/42009457/e544767d-17c6-4ffd-90d9-89846a684178)


![DARK MODE dark surround](https://github.com/w3c/csswg-drafts/assets/42009457/bfc8fd0a-3e84-4ff9-9d21-39885260bf94)


## Summary
- For SDR displays
    - In light mode, text is ideally full black `#000`, but the background is better as off white, 80%-85%, with peripheral elements at `#fff` to anchor adaptation.
    - In dark mode, text brightness needs to be relative to the background, and the background is ideally relative to the larger surround.
        - Currently testing $L^c\ -85$ to $L^c\ -90$ as maximums for dark mode text.

