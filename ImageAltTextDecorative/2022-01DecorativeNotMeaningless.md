# Jan 24, 2022
Comments regarding decorative, background, divisional, and alt text.

## Pure Decoration?
From a design point of view, what does "pure decoration" actually mean? That term as stated seems to imply that decorative embellishments have no meaning, but at least in a classical design sense you never put something into a design without a purpose or without a reason, even if that reason is hard to articulate lexically.

<img alt="flourish" width="400" src="https://user-images.githubusercontent.com/42009457/150781466-d7e34382-82f4-4144-ae7b-78fc3f4841e2.jpg">

### The purpose of adding a flourish is among other things, to convey a mood or a tone or an emotion.

<img alt="a flourish design element that implies an essence of floral leafs" width="400" src="https://user-images.githubusercontent.com/42009457/150781411-ddd061ee-82af-4e94-bab4-74696f52574c.jpg">


But — from a practical standpoint, how should these be described?

- The alt for ` #1` is "flourish"

- The alt for ` #2` is "a curvilinear flourish design element that implies an essence of floral leafs"

And let's say there are many on the page (such as a page for a wedding reception) — the question I'm posing is not if flourishes should be labeled, but to what degree? As I try to use voiceover on MacOS more often  for body text,  I find it challenging to deal with all the extraneous elements on the page when I really just want to hear the main content text. 

And then there is the issue of things like the use of dingbat fonts or flourish fonts — something that voiceover seems to stumble on, not sure about other screen readers.


### And here's another example:

<img alt="A Brief History of Computer Punch Cards on a paisley background  " width="400" src="https://user-images.githubusercontent.com/42009457/150789840-d59eca9e-188b-4330-88af-d00ac852e310.jpg">

At first glance one might say that's a decorative background... except that paisleys came from the development of the Jacquard Loom which used what were essentially a series of punch cards to control the loom to create these intricate patterns. As such, it would actually be best for an alt text to say something like _"an image of a paisley patterns made possible by early automated loops, using a forerunner to  punchcards."_ 

But This example is here for another point: as shown, in an actual page it would probably be as a background image, and at present those don't accept alt text, though that seems like a property that needs to be added. The use of background images as an image container is useful for responsive design in a way the regular img tag is not.


## Text to Speech
@bruce-usab 
> _With regard to your two flourish examples, please ask a few people who use screen reading software as their default UI as to what they would recommend as the value for the alt attribute or Accessible Name with those two examples._

I've been trying to climb the learning curve of Voiceover, the screen reader on MacOS, as I'm having an increasingly difficult time with just basic reading — so far, all I can say is OMG this is frustrating! If I'm still atound by the time I'm done with the APCA project, I think I'm gonna need to start a screen reading project LOL...


> > _From a design point of view, what does "pure decoration" actually mean?_
> _It is the label (e.g., title or shorthand name) given to a specific concept and term of art from WCAG. Nothing less, nothing more. Please do not overthink it, even if you are a designer! Please reference the glossary definition._

It was a rhetorical question really... 😎

> > _.."an image of a paisley patterns made possible by early automated looms, using a forerunner to punchcards."_
> 
> _That sort of detail belongs in plain text in the footer, or maybe on an "about" page. It is compelling trivia that needs to be available to everyone, not hidden in an alt attribute, and which is not repeatedly forced on _only_ those visitors who happen to be using screen reading software._ 

This was also sort of my point — this would probably be (or should be) a caption to the image... Or a pop-up perhaps...

And it brings up a thing I sometimes talk about relating to inclusivity, that sometimes is misunderstood, so I'll try to tread carefully here. Among the thought experiments I have going on, one is the "how can wider adoption be encouraged" relating to the general gestault of accessibility. The answer I keep circling back to is broadening scope. At the moment, scope as I understand it is largely centered on providing descriptions for screen readers, so that those that can't see the image have at least a description. At the moment, AFAIK, the technology isn't there for some thoughts relating to broadened scope BUT:

### Cognitive and Understanding
We've been talking about about the purpose and intent of some decorative elements on a page. Sometimes these may be cultural and not immediately understood by all. Or for those that have other visual issues, such as [Prosopagnosia](https://www.nhs.uk/conditions/face-blindness/) they may benefit from a more detailed lexical description. Or other cognitive issues that interfere with understanding context of a given image. Not to mention the usefulness in "reader mode" and in conditions where the image is missing due to bandwidth or device issues...

These are other good reasons to have alternate text — only for the most part, the alt text is not itself accessible outside of screen reader use, though I can be with an extension, but not as a standard user agent feature.

The inclusivity point: **if a standard aspect of alt text was readable via a pop up like a tool tip, or other accessibly means, it** would find a larger audience. A broadening of scope that would be helpful to a larger group, and such broadening of scope increases the need and the demand. Increased demand means increased adoption.






