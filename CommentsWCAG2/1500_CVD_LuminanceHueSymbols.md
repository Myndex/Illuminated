### I disagree with these changes IN PART.

While I certainly agree with the spirit of some of the changes, there is need of further revision IMO.

On commit **2622d7f**:

I agree with the added word sighted: _...ensure that all **sighted** users..._

But I disagree with the removal of "text only displays". These types of displays certainly affect sighted users. The world is a big place, while here in the US we may rarely see text only and limited color displays in direct use, we can't say that is true for the rest of the world. 

And we do have a "text-only" here when we enter reader mode that ignores much of the CSS styling including color as in hue.

And if we are going to open this up for a change, we can clarify and modernize further. Here is a suggested alternate paragraph:

      <p>Color is an important asset in the design of Web content, enhancing its aesthetic appeal,
         its usability, and its accessibility. However, some users have difficulty perceiving color. 
         People with Color Vision Deficiency may be unable to recognize different hues, such as an
         inability to tell the difference between red and green. People with partial sight, cognitive and neurological
         impairments, as well as many older users, can have functionally limited color vision. People with these and
         other visual needs may use their own CSS styles that overwrite the author's original colors. Further, people
         using text-only, limited-color, or monochrome displays and browsers will be unable to access
         or understand information that is presented only as a difference in color.
      </p>

Later in this commit is this note, quoted only in part:

        <p>This criterion does not directly address the needs of users with assistive technologies.
            It aims to ensure that sighted users who cannot perceive color can still understand content.
            How information is conveyed to assistive technology users is covered separately ......

This may be true if assistive technologies only means screen-readers. However I consider extensions like "DarkMode" and other user adjustments to be assistive technology as well, and if we consider those then this SC does still apply, and I suggest it does apply **_to all sighted users_**. WHich brings us to this sentence:

         ...ensure that sighted users **who cannot perceive color** can still understand...

All sighted users can perceive color with the very rare exception of "Blue Cone Monochromats" who have no red or green cones and are the only ones that are truly "color blind". But they are not only incredibly rare (one in a million) they also suffer a profound impairment as blue cones are very poor in resolution among other things. They need assistive technology regardless.

The remaining individuals with Color Vision Deficiency still perceive color. They have a more limited gamut of color, and difficulty in differentiating between hues. [I have a CVD simulator that demonstrates this clearly.](https://www.myndex.com/CVD/sRGBCVD) But again, this SC does not only apply to CVD, it applies to all sighted users, and is primarily a restriction from coding information strictly with hue, which is bad design practice and I'll get to that in a moment. The statement "...who cannot perceive color" is repeated a couple times. All need to be revised to something like _"those who cannot differentiate between some color hues."_

### Objection RE: Note on Coding Information

**I most strongly object** to the note of commit 9b74ac0, which implies that luminance contrast is useful for coding. **IT IS NOT.** Multiple international standards including the FAA/NASA have restrictions on coding using luminance contrast, for good reason.

### Let's discuss.

Luminance contrast (light/dark, disregarding hue and saturation) is critical for things like letters, fonts, objects, so that the visual stimuli gets through the thalamus, and in the visual cortex is filtered by V1, sent to  V4, and then to the VWFA (Visual Word Form Area) for decoding as whole words and letter pairs. For this to happen efficiently, we need ample luminance contrast, and hue/chroma contrast is not much a part of this.

But that does not mean that luminance contrast is useful for information coding based on contrast alone, and if in combination with hue only to support the hue coding, and the 3:1 reference is unsupported here. And luminance contrast should not be a part of this SC at all, it is not relevant (other than luminance contrast shall not be used for coding information). Luminance contrast can be useful for things like "focus" but not so much for things like "good/bad".

Something this SC does not appear to touch on (perhaps I missed it) is that color hues are also NOT absolute in meaning and are interpreted differently in different cultures. **Words and symbols convey meaning.** Color hues do not reliably convey meaning, and luminance contrast does not either (with the possible exception of "on/off").

### Summary:
- Luminance contrast is important for details of content such as fonts, words, drawings of objects... But luminance contrast itself does not convey the meaning, the meaning is conveyed by the details in the stimuli. 

- Color as in hue/chroma/saturation is less important for "details" and lexical processing. Hue/chroma is a third the strength of luminance in terms of contrast and resolution (this is how image data compression like jpeg gets away with throwing out most of the color information in an image).
    - Color hue & sat can be useful for coding information, but a number of limitations exist, some of which affect all users regardless of impairment. 
    - Thus color hue can not be the only informational coding.
    - A STOP sign is not just a big red octagon. It is emblazoned with the word STOP. And here again, we have multiple information codings. The sign is reflective red, but it is also an octagon, and it also has a lexical, literal statement of meaning. 

- Meaning is found in words and symbols.
    - Luminance contrast serves to makes _THOSE_ words and symbols readable, but does not add meaning. However, consistent contrast of specific items (such as roads on a map) can help make that information more clear and organized.
    - Color hue/chroma can add meaning in some cases, but it can also detract and interfere with understanding if used improperly. For instance, what does Cerulean Blue mean? The answer is unknown without a legend. Color does not have universal meaning on its own.

- There are other kinds of contrast: size, shape, motion — but contrasts are not really relevant for this SC, which is about information coding. Contrast is better covered elsewhere.

### SIde Bar on CVD 

Keep in mind that color as in hue is already full of luminance contrast. Full green #0F0 is more than three times the luminance of full red #F00. But someone with protanopia won't even see red on one of the new UHD monitors. in eRGB, they see red a bit darker than we do, but most important can not distinguish between red and green. Protan and Deutan are the most common CVD types, and thus colors that vary only in their red to green ratios present a significant problem for them.

Again, luminance contrast does not convey information, but makes lexical information more clear. Examples:

Here is red and green, set to the same luminance (no luminance contrast). It does not matter if you have CVD or not, it is plainly hard to read:

![Screen Shot 2020-11-09 at 8 21 41 PM](https://user-images.githubusercontent.com/42009457/98629096-f8562500-22cc-11eb-8063-341dc9f358fb.png)

But how do people with CVD see it?

![Screen Shot 2020-11-09 at 8 19 55 PM](https://user-images.githubusercontent.com/42009457/98629133-0a37c800-22cd-11eb-9d5d-3c4465e19055.png)

There's an odd fact: the protanopia sees it BETTER because they see red darker, it actually improves their contrast. But it is literally unreadable to the deuteranopia and might as well be invisible.

Now let's boost the luminance contrast to a reasonable 80 (APCA):

![Screen Shot 2020-11-09 at 8 21 04 PM](https://user-images.githubusercontent.com/42009457/98629234-45d29200-22cd-11eb-9e60-bc39bbcd945d.png)

This contrast boost did not add any real "information" it just made the words easier to read.

![Screen Shot 2020-11-09 at 8 20 49 PM](https://user-images.githubusercontent.com/42009457/98629282-5daa1600-22cd-11eb-8f15-520cd65f3043.png)

And both protan and deutan see it better as well. Now let's flip it around:

![Screen Shot 2020-11-09 at 8 55 56 PM](https://user-images.githubusercontent.com/42009457/98629609-1708eb80-22ce-11eb-92f4-85a66d5d4305.png)

About the same APCA 80 contrast here...

![Screen Shot 2020-11-09 at 8 56 02 PM](https://user-images.githubusercontent.com/42009457/98629644-2851f800-22ce-11eb-91f5-086201045a54.png)

But again the deutan and protan can really glean no "information" because they cannot distinguish red from green. The luminance contrast does not convey information, it just make information clearer. (Sounds like a BASF commercial, LOL).

Andy






