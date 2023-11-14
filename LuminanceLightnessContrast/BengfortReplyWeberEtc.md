# Q&A on Weber
The following exchage was in reply to my article ["The Realities And Myths Of Contrast And Color"](https://www.smashingmagazine.com/2022/09/realities-myths-contrast-color/)

> ### Tobias Bengfort wrote — september 12, 2022 18:39 #
> _Thanks for this great article with a lot of helpful information._
>
> _The only thing I don't agree with is that _"WCAG 2 contrast maths do not predict the contrast of text in accordance with human perception"_. WCAG 2 is based on the Weber-Fechner law which is an older but still very useful model of human perception._
>
> _WCAG 2 is optimized for dark viewing conditions, APCA is optimized for bright viewing conditions [See: APCA  (directed to correct analysis)](https://github.com/Myndex/apca-introduction/blob/main/analysis.md). That is the reason why the two approaches have different results for dark color pairs. This doesn't mean that WCAG 2 is wrong._
----

## Andrew Somers (Article Author)

Andrew Somers (Article Author) wrote — september 13, 2022 18:03

Thank you for the comment Tobias, though I believe there are some misunderstandings here.

### 1\) Weber is a 180 year old formula
It has been used to determine the threshold JND (just noticeable difference) of any given human perception (not just vision). For vision this means the narrow region between visible and invisible. Here, Weber is still useful in certain research applications.

However, Weber fails to predict supra-threshold stimuli, and is also inaccurate for the prediction of lightness perception, which Stevens, et alia, pointed out in the 1960s.

Also, Weber essentially needs the background stimuli to be near the light adaptation of the eye — as such, it has been used historically for measuring dark text on a light background (i.e. paper white with dark printed text).

Today's dynamic web content requires a contrast measure that is perceptually uniform across the entire visual range, and especially for the high spatial frequency of text, and at supra-threshold levels.

Weber is not perceptually uniform across the visual range, and becomes increasingly inaccurate or non-uniform when the background departs from the adaptation level, and for supra-threshold contrasts.

So while Weber is useful in a research context for JND, it is not so as a practical method for guidance to designers.

### 2\) Your Statement:
> _"WCAG 2 is optimized for dark viewing conditions, APCA is optimized for bright viewing conditions"_

This is not true, and is a misunderstanding of the relevant math and concepts. WCAG 2 is not "optimized for dark view conditions" that is false. Both WCAG 2 and APCA were, and are, intended for the same bright environment.

In the development of WCAG 2's contrast, an attempt was made to constrain the results and to account for screen flare from a bright office environment. This was the intention of the 0.05 Y addition, which was taken from the IEC standard's definition of the general viewing environment, with an ambient illumination of 350 lux which is a "bright office".

While WCAG 2's (Ya + 0.05) / (Yb + 0.05) was an attempt to optimize for a bright office space, the failure is that it is still not perceptually uniform across the visual range, and especially for supra-threshold text, which is what we are most interested in. Like the Weber it is based on, it mainly works when the background is lighter than #bbb.

APCA — W3 is optimized for the same bright office, 200 lux to 350 lux, but APCA does so using math that follows human perception of lightness & supra-threshold contrast of high spatial frequency stimuli, in other words, text. There are other versions of SAPC, APCA, and SACAM that are optimized or adjusted for, or dynamic to, different environments, but that's outside this discussion.

In this article above, I demonstrate that under the section "Spatial Cases" where you can see the relationship of spatial frequency to contrast perception.

It is spatial frequency that is the primary driver of contrast perception, not color. Color distance is subject to contrast constancy and contrast adaptation. What is more important is understanding where/when contrast constancy applies, and what a given spatial frequency requires in terms of color or luminance contrast in order to accommodate the reduction of contrast sensitivity at higher spatial frequencies, especially where text is involved.

### 3\) Invalid Analysis
Your analysis and visual examples at your repo are not using an approved APCA or "analyzing" it per APCA specifications. The examples you created in the "introduction" readme are not following APCA guidelines. I forked the repo and made corrections, and particularly did a line-by-line critique of your analysis page, and corrected the introduction examples to be in line with the actual APCA math and guidelines.

### 4\) Your Statement:
> _"That is the reason why the two approaches have different results for dark color pairs."_

No, as mentioned this is a misunderstanding of the underlying concepts or revisionist in nature. "Optimized for dark" is not the genesis of WCAG 2.

WCAG 2 can not calculate for Dark Mode, this was known and objections had been made back in 2007 when it was developed, but dark mode was not as popular as it is today.

Today, and with the understanding that dark mode is beneficial for many types of impairments and for reducing fatigue, it is important to have a method that is perceptually uniform for text on a self-illuminated display that can calculate contrast across the visual range, and especially for readability.

### 5\) Wrongness
> _"This doesn't mean that WCAG 2 is wrong."_

WCAG 2 contrast can not calculate correctly (or usefully) for dark mode, and is also inaccurate for inverse text polarity, and low spatial (large) elements, and further, really only works when the background is lighter than #bbb, with dark text. Thus it is "wrong" for a significant portion of the visual range, and some of the related SCs are "wrong" in not considering spatial frequency with the emphasis it should be.

TO BE CLEAR: The bulk of WCAG 2 SCs are an important set of guidelines for accessibility, but the well known problems with the WCAG 2 contrast SCs cast a dark shadow on the rest of the guidelines, and this is why we have spent years and considerable research effort in developing new methods to meet the demands of modern technology.

I hope this clarifies these points.

Thank you for reading,

Andy
