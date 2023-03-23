I’ve been working with light, color, vision, filmmaking since I was a child, and over my lifetime I can tell you the science of visual perception has changed substantially and continues to change. It is still an evolving science.

It is also a much smaller community that I really realized. 

Regarding dataviz and cognitive, motor, motion… yea, this is big: unless the data is simple and a simple chart fits on a screen, there’s going to be a lot fo zooming, scrolling, etc… 

## KEY BITS relating to dataviz:

For TEXT, for best fluent reading speed, there is the concept of the minimum critical size and minimum critical contrast (Lovie-Kitchin). Critical size is ~2.4x the acuity threshold. Critical contrast is 10x the CS threshold of JND, for “normal” fluent reading. It needs to be 20x the threshold for maximum speed/comprehension. 3x the thresh. is fine for sub fluent “spot reading”.

For TEXT, it is all (and only) about achromatic luminance contrast. That’s processed first in V1, and gets steered through V4 to the VWFA (visual word form area) where letter pairs and whole words are recognized/filtered, then sent to  the lexical processing. Once here, it’s about what the letters mean. “Stroop” tests show that if the word is “red” but the color of the letters are actually green—if you ask the subject the color of the letters, they respond with “red”.


So then, for non-text, obviously the VWFA is of no use. Or is it? Let’s divide non text into some broad categories: intrinsically semantic, abstractly semantic, functional/indicational (focus), and divisional/identifying/containing.

So, intrinsically semantic is icons with an embedded meaning:  
# 😳 🏈 📺 📫 🔓 🕔  
in these cases skeuomorphism is the obvious connection to semantics.

But what of 
# ⚙️ ☰  ➡️ ⬅️ ⏩ ⏮ ⏏️ 🔀 ♻️ 🔆 🔅 

What does the gear mean? Mechanical? Motion? We’ve learned it to be preferences usually. Then next, a spiritual symbol that is the hamburger menu… completely meaningless and abstract, but has developed into a semantic meaning of “hey there’s a menu down here”.

Of these which means stop, which is do not enter, and which is a general no? 
# ⛔️ 🛑 ⭕️ 🚫  
Cultural dependencies change that answer. Is this a house or a passing grade? 
# 🈴  
 If this is “don't": 
 # ❌  
 then what is this: 
 # ❎

And graphics in a chart like lines or bars of the data are abstract but convey meaning and so have a certain semantic value.


All of these next are abstract, but some of these might be usable in a semantic way:
#  🔳 🟥 🔵 🟢  ◉ ❇︎ ✻ ➤ ✣ ◢  ◿ ◌ ◐ ❖ ⌱ ⎈ ⍉ ⏚ 

In an electrical schematic, ⏚ means ground. In a mechanical drawing, ◿  means fillet.


But some like these are more likely to be used in a functional way (radio button, etc…) or indicating a meta state.
# 🟥 🔵 🟢  ◉ ◢ 


 # 🔳  
 the box around a form is divisional or containing
 
 # ❖ 
 the bullet for a list is identifying

These last ones are non-semantic, carry no real informational value, serving only to divide, organize, contain, or mark points in text, etc.


My point, the contrast needs for all of these are all very different based on use case and the underlying need to convey meaning, or merely to divide and organize, or somewhere in between.

So next, we know that everything gets processed first in V1, and that is where luminance contrast is determined, and its driven by spatial frequency. The thin-ness.thickness instructs us on the amount of color/lightness distance is needed, and also if we can differentiate with hue sat, or if luminance differentiation is important.

Luminance holds al the fine details, color is very low frequency, and a third the revolution of luminance.

### FOR A PIE CHART:

The the very thin pieces of pie need high luminance contrast. The very big pieces of pie need much less luminance, and do better with significant hue changes. But very thin pieces do badly with hue changes, as hue detection works on large bits (low spatial frequency).


### Neurological processing
While text is processed in the VWFA and lexical, object recognition, and other recognitions, are processed in other areas of the brain. Motion is processed also separately. Color (hue sat) is processed separately and later from luminance.

So, the specific rules for text and critical contrast for reading are a little different for dataviz and non text, and it also depends on the degree of semantic information, or the functional use, of the graphic.

That’s the bird’s eye overview.
