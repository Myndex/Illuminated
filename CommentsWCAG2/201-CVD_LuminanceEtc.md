### Just a footnote to this thread:

It is useful if not important to make a clear distinction between **luminance**, a measure of light, _versus_ **color** as in hue and chroma.

**Luminance** is processed in the visual cortex separately from **hue** and **chroma**, and they have markedly different effects sensorily and cognitively depending on the perceptual context. 


**Luminance contrast** is critical for details. Text, edge detection, these all require ample luminance contrast. However luminance differences are particularly poor for "coding" information. As a side note FAA standards limit luminance coding to three levels: black, mid grey, white.

**Hue/Chroma contrast** is nearly worthless for detail. It has a third the strength and a third the resolution of luminance, in fact in some combinations it can interfere with details like text. But hue/chroma is good for information coding. "Color coding" is ubiquitous. 

Without getting further into the details, there is an important divide between understanding the use and functionality of luminance differences vs hue and chroma differences. For that reason they should be kept separate and referred to separately in SCs and guidelines.

-----

Hi Mallory @StommePoes and Patrick @patrickhlauke 

The gist of my above comment is simply that luminance and hue/chroma (or saturation) should always remain separate in terms of standards definitions and user needs.

### I'll wager 3:1 in skittles that you'll have a hard time seeing links in the first example below.
That said, a luminance difference of wcag 3:1 relative to a black text as a way to "code" the information that it's a link is barely perceptible even for the nearby text‚ in part because ratio math tends to over-state the ratio for very dark colors, but also because static luminance difference relative to a related and similar stimuli is very hard to perceive for a variety of reasons (contrast constancy is probably applicable) 

What we are talking about here is something like #595a59 text next to #000 text on an #fff background.

Here is that specific example. Let's play find the links: <img width="503" alt="Screen Shot 2020-12-13 at 4 44 00 PM" src="https://user-images.githubusercontent.com/42009457/102029357-0a5f3380-3d63-11eb-96d3-078fedb3fbc5.png">

There are at least five links in that text, how long does it take to find them?  If you are in dark mode, you'll probably find them faster than in regular bright BG mode. Regardless the link text is WCAG 3:1 contrast to the plain text, and it's clearly a terrible way to identify links. I know where they all are and I'm still having a hard time differentiating, oh but then I'm just an old guy with impaired vision... ...Oh wait....

Now look at this example:
<img width="503" alt="Screen Shot 2020-12-13 at 4 57 25 PM" src="https://user-images.githubusercontent.com/42009457/102029766-99208000-3d64-11eb-852f-f493ba4d2b0e.png">

These links are much more visible so as you might expect they fail WCAG 2.x....   The unvisited links are #03d and the visited links are #80a, both well under 3:1 yet far more visible... oh but it's color so it must be bad right? Not really, these are colors that CVD types see, because **CVD types still see colors** despite the undue burden of society labeling them as "color blind" (which by the way is a lie. And ableist. And if we could all stop using "color blind" and instead use **"reduced color sight"** or something that would be nice).

### Here is how people with the most severe dichromatic CVD perceive these links:

<img width="1086" alt="Screen Shot 2020-12-13 at 5 01 07 PM" src="https://user-images.githubusercontent.com/42009457/102030080-17c9ed00-3d66-11eb-852d-c08633002a0a.png">

Hmmm.  The VAST majority of CVD types have NO PROBLEM (deutan/protan) differentiating the links from not links. Tritanopia has the most trouble but still easier than the 3:1 luminance version. And tritanopia is very rare (somewhere around 1 out of 35,000 people). Achromatopsia will have trouble with the links, but they also are extremely rare (1 in 100,000) and sadly they have a **_greater_** struggle with low vision and photophobia so they need AT no matter what.

Am I saying that 99.9998% of sighted people can distinguish these **colored** links better than the 3:1 luminance links?
## Yes I Am.
Regarding system level contrast helpers: I don't know about WHC, but MacOS High Contrast does not impact the color link differentiation, and invert works as well.

### What Does All This Mean
Mainly that the notion that color as in hue/chroma should be disregarded for informational use is too absolute. Those with CVD can still distinguish colors, but have a much more limited gamut. There are specific ways color (hue chroma saturation) can enhance accessibility, yet it is being disregarded in 1.4.1 and G183, and the promoted "fix" is anemic at best. As I stated in the survey, G183 is simply incorrect in multiple areas and could use a ground up rewrite.

Thank you for reading,

Andy



-----




Hi Patrick @patrickhlauke  Hi Mallory @StommePoes 

Yes, I realize it's been there forever, and unfortunately is part of the several items that a "out of whack" for lack of a better phrase.

I am trying hard to not get "too" involved in WCAG 2.x SCs, because my focus is on bringing correct or best practices to WCAG 3, and this is one key area of my research as part of the total Visual Contrast for Readability and Accessibility.

I do however try to drop in information from the ongoing investigations — if it can not be reconciled with WCAG 2.x then at least for an indication of the direction the work is leading to. I "am" trying to think of ways that WCAG 2.x can "tip toe" toward perceptually correct standards. 

A reason that we moved all of Visual Contrast to Silver is that it is a paradigm shift, and the concern is that is was too much of a shift to modify WCAG 2.x — the same is true for color (hue/chroma). In the examples above, I showed very specific colors that work, but the available colors are not intuitive, not related to any existing WCAG2.x math, and the color module has not been added to the APCA math yet, either, for a number of practical and developmental reasons.

Ans if you thought that luminance contrast was a big can of worms, hue/chroma/sat contrast  is a barrel of monkeys drinking redbulls and vodka. Hue/sat is tied to luminance, and hue/chroma/sat can interfere with readability while improving discriminability — it is another conflict of best practices.

But an intermediate "tip toe" step could be to define a "CVD Safe" color set, with narrowly defined use cases, such as inline link text for 1.4.1, but again, I understand if that just is not doable within the WCAG 2.x paradigm.

### So Why Am I Over Here Picking on Things?
I mention all of these things so we can all start to see a brighter future direction (see what I did there?), and I realize I may not be fully in sync with some of the 2.x changes,  but if I can only get one thing across, it's the use of the term "Color Blind" and IMO one of the important "tip toe" steps is getting terminology right. 

**99.998% of those with CVD are not color blind.** They only have a reduced color discrimination. Even the most profound deuteranope or protanope can still see hundreds of thousands of colors (far shy of the many millions of normal vision, but not devoid of color). Only the very rare achromatopsia is monochromatic, and that small group has other more serious vision problems that require AT.

- Instead of **Color Blind**, we need a new term that is not so completely incorrect and ableist. The medical terms for some disabilities are changed as often as every 30 years or so, It should not be too difficult to change colorblind. Some ideas here to float (work in progress):

    -**Hue affected**, short for hue affect disorder
    -**Color Impaired**, short for impaired color vision
    -**Chroma deficient**, short for chroma deficient perception
    -**Hue limited**, short for hue limited vision disorder
    -**Color dark**, short for diminished color vision
    -**Chroma reduced**, short for reduced chroma perception

Some things to think about that I hope add to the dialog...


Andy



------


Hi Bruce @bruce-usab 

> I will also confess that I am a fan of keeping some version of [T183](http://www.w3.org/TR/WCAG20-TECHS/G183.html). How do folks feel about increasing the required contrast from 3:1 to 4.5:1?

I think part of what I am not getting across is the issue of identifying a link without impacting readability, which then is also considering the future compatibility with the work we are doing in Silver. This fails in both regards as it makes the text less readable, and is counter to the emerging Silver guidelines.

> FWIW, there exactly _two_ shades of true grey that can provide 4.5:1 contrast against both black and white, [757575](https://webaim.org/resources/linkcontrastchecker/?fcolor=757575&bcolor=FFFFFF&lcolor=000000) and [767676](https://webaim.org/resources/linkcontrastchecker/?fcolor=767676&bcolor=000000&lcolor=FFFFFF).

But also FWIW, that math is still wrong. Perceptual middle contrast is `#aaa` and not `#777`, and I have a live interactive demonstrator here:

https://www.myndex.com/SAPC/CommonBG_SAPC08

Move the large "background control" slider so that the black text and the white text is equally readable. Depending on ambient lighting and screen calibration, it should be close to `#aaa`, typically between `#a0a0a0` and `#b8b8b8` depending on polarity effects which are part of this series of experiments.


> I find the FAA note interesting. @Myndex can you provide the cite to that? That seems quite reasonable to me!

Funny enough, discussed some FAA related guidelines in #675 last year, The FAA materials are largely referencing MilSpec and NASA research, and is fairly authoritative within their defined use cases.

I remembered it slightly differently, on review it is related to some older specs and ATC and not current flight deck specs:
<img width="420" alt="Screen Shot 2020-12-15 at 5 23 44 AM" src="https://user-images.githubusercontent.com/42009457/102680708-9613fe00-416f-11eb-9ed1-746d98d4ed32.png">

In context, it is referring to a bright/dark pair of some color such as for enabled/disabled (think hover state). This idea should not be applied to black text on a white background as I demonstrated earlier. The psychophysical aspects relative to the high contrast needed for readability prevents this as an effective solution. 

The most recent human factors book is stricter regarding color overall, probably due to the greater use of color EFIS, but also likely due to the Flight 1478 727 crash that was caused in part by one of the pilot's CVD and his misinterpretation of the glide slope PAPI and subsequent impact with terrain.

https://www.ntsb.gov/investigations/AccidentReports/Reports/AAR0402.pdf

### Latest FAA Human Factors
**Selected tidbits on color**

For the flight deck, luminance coding or tint/shades of a color should not to be used FOR CODING per the latest flight deck human factors manual, which also limits the number of colors for color coding to six:

<img width="500" alt="Screen Shot 2020-12-14 at 8 33 21 PM" src="https://user-images.githubusercontent.com/42009457/102680760-218d8f00-4170-11eb-96c3-4ba975d7cbd8.png">

### And other related FAA color:

Population incidence indicates deutan and protan are the primary concern:
<img width="400" alt="Screen Shot 2020-12-15 at 5 17 38 AM" src="https://user-images.githubusercontent.com/42009457/102681576-518c6080-4177-11eb-82b2-959dec707860.png">
Tritans are so rare it has been very difficult to find test subjects to even do research, so actual practical research is limited. But we are all tritan in our fovea, and elderly eyes yellow causing a loss of some blue response — the classical design guidelines regarding how blue should be used is helpful to all (blue on black is bad, pure blues on white are good).


### Specific to WCAG 1.4.1:
<img width="600" alt="Screen Shot 2020-12-14 at 8 14 01 PM" src="https://user-images.githubusercontent.com/42009457/102681767-0d9a5b00-4179-11eb-8424-82061c419de1.png">

<img width="600" alt="Screen Shot 2020-12-14 at 8 34 42 PM" src="https://user-images.githubusercontent.com/42009457/102681792-4e926f80-4179-11eb-9e3f-183f078ff32d.png">
<img width="600" alt="Screen Shot 2020-12-14 at 8 36 01 PM" src="https://user-images.githubusercontent.com/42009457/102681794-4fc39c80-4179-11eb-816c-8798395b89ac.png">


### Design for Mono and Bad Color Pairings
<img width="600" alt="Screen Shot 2020-12-14 at 8 40 58 PM" src="https://user-images.githubusercontent.com/42009457/102681795-4fc39c80-4179-11eb-9c92-8f0c8c3bdc72.png">
<img width="600" alt="Screen Shot 2020-12-14 at 8 12 18 PM" src="https://user-images.githubusercontent.com/42009457/102681766-0d01c480-4179-11eb-866d-1e10cad6a0e2.png">

### Cognitive/Discrimination
<img width="600" alt="Screen Shot 2020-12-14 at 8 11 28 PM" src="https://user-images.githubusercontent.com/42009457/102681764-096e3d80-4179-11eb-83cc-b2ba2d29f4ec.png">




-----


Hi Mallory @StommePoes 
> _True, but I would hope neither 1.4.1 nor whatever new is coming down the line for 3/silver/whatever _limits_ itself to CVD. I think I have full colour perception in general, yet 1.4.1 matters to me personally._
AND
> _....however it leaves out those who have other reasons for not perceiving colours who generally are sighted...._

The work we are doing is definitely not limited to CVD, and CVD is only one small part of the total puzzle. But you have me curious, which non-CVD color perception issues are you meaning here? Can you describe please?


> _I'm wondering if this can be helpful for the (in other tickets) somewhat related question of when the difference between, for example, a "filled star" vs an "empty star" (an example used on the 1.4.11 Understanding page) is considered a difference of "colour" vs "contrast". ....With only 3 levels, this should end up not only being simpler to separate contrast issues from other visual perception,...."_ 

As I mentioned above to Bruce, I remembered the three level rule a bit differently, and it was an old standard and not part of the current human factors. Luminance coding should not be used (in general) I see a use case for "active/inactive" components to have a light/dark version of a color, but I'd see that as say, a bright green vs a dark green, and using colors in the middle of the luminance range, not "black text vs not quite as black text."

And I may have gotten off point as I tend to sometimes. The POINT is that luminance contrast and color (hue/chroma) are processed by different parts of the brain, and also serve different purposes. Luminance contrast is the key factor in edge detection, and resolving fine detail like fonts. But it is less useful for discrimination in terms of meaningful coding, and object recognition. Color as in hue/chroma however are very useful for coding meaning and object recognition.

Contrasts of size, shape, position, motion, state change are also good contrast types for coding certain types of meaning, nevertheless, all of these also can be affected by various impairments.

There is no one-size-fits-all in this area, and something helpful to one could be harmful to another. The ultimate solution is a better implementation of customization for all.




-----


Hi Patrick @patrickhlauke 
>..._my intent at this point was only to surface what has always been latently there since 2.0, just never made quite explicit enough._

Yes sorry Patrick, I had never looked critically at G183 until this, and all this stuff jumped out at me which is why I brought it all up. Probably will just be fixed in Silver from the looks of what is needed.

### Summary Comments
also to @StommePoes @bruce-usab 

It is worth noting in an ironic sort of way that the CSS for at least some parts of W3's site technically fail here with links. 

The unvisited links are essentially the same color as the surrounding text. There is an ultra thin underline made using bottom border, but the color is very light, coupled with the thinness is hard to see (certainly for me, young eye probably have no problem).

Then the visited links are blue, just like the common unvisited links. Visited blue links combined with the hard to see unvisited links is a cognitive failure for EVERYONE. If you expect unvisited links to be blue, and the only links you actually see are blue, then you will assume those are unvisited links, and may further not realize the actual non-visited links which are cleverly hidden.

Fortunately the hover-state helps to clarify, but hover states are not useful for touch screen use as noted.

### Recap
Here's the upshot then I'm going to leave this alone:

- coding inline text links is a unique type of coding, and important as a core feature of the web. 
    - It is a non-text coding for text itself.
    - because it exists directly on the text, it is constrained by the same limitations as those for text readability, meaning it needs to meet the same readability contrast.
    - other coding methods such as shape or size are not practical or interfere with readability, as can underlines, excessive bolding, or other style changes. Thus a balance is needed between identifying the link and not interfering with the readability of the text.
- Luminance coding in itself is ill advised and ineffective, in addition it interferes with readability contrast.
- Deutan and protan still distinguish many colors, such as blue vs yellow. 
- design-wise for all users, pure blues should be the darkest color of a pair.
    - on a light or white background, pure blue text such as `#00d` is close to black, and does not hamper readability (in fact can reduce glare for some people by reducing the blue channel detail).
    - Blue `#00d` is far more distinct to 99.998% of sighted users than blue `#069`,  but `#00d` fails the G183 luminance while `#069` passes. 
    - Blue `#069` is only possibly, slightly more distinct to 0.002% of sighted users, while **harming** distinction to 99.998% of users.
- On a black of dark background with light text blue cannot or should not be used. But yellow can have the same usefulness.

And finally:
- Because of the uniqueness of an inline text link, the needs associated with readability require a balance with link identification. 
    - of all the things that need distinction, inline link text in blocks of body text often call for the most minimally invasive approach.
    - excessive link identification in body text has a negative impact from a cognitive perspective by increasing the apparent chaos, distraction, and disorganization.
    - it is convenient to think of inline text links as the footnotes of our day, used to connect to the minutiae of supporting information without bogging down the reader needlessly. The fact a link exists is important, but not important enough to interfere with readability.
    - The fact an unvisited link exists is more important than indicating if that link has been visited. The case can be made that a visited link could be reduced in distinction to be helpful.

None of this is effectively addressed by G183, which may in fact be harmful in the manner it attempts to portray the issues.


Thank you all for reading and discussing this, if not for WCAG 2, this discussion is still useful for Silver development.

Andy



-----


