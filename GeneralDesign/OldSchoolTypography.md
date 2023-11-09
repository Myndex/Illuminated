From the [LVTF Mailing List](https://lists.w3.org/Archives/Public/public-low-vision-a11y-tf/2019Oct/0016.html)

Hi Shawn, my comments inline below:

> _On Oct 15, 2019, at 5:59 PM, Shawn Henry <shawn@w3.org> wrote:_
> _Oh, dear, this got my attention and brought back memories!_

Memories!!

Circa 1982 working in the layout room of a tiny local paper, before DTP and WYSIWYG, when there was no such thing as laser printers — we had to send things out to be typeset because there was no cut and paste text, it all was typed in by the typesetter… and we'd get them back in a day or two, cut them up with razor blades, put hot wax on the back, and stick the pieces onto a nonrepro blue grid paper on a light table.... ... UPHILL BOTH WAYS!! 

The typesetter would set kerning and tracking — if it was full justified columns, then all form of spacing would be adjusted to accommodate. Space after period is one place that “extra” expansion can be had without causing problems.

Though today, it isn't just WCAG and CSS that indicate avoiding full justify — print typography too, as there has been plenty of research showing the justify left/ragged right, and avoid hyphenation, reads better for the majority of users. My personal preference now if I am setting a book for instance is left just/ragged right BUT also individually adjust tracking & word spacing of select lines to ease the ragged right into just a little less ragged for those weird lines that just won’t wrap the way I want.

Another thing we did NOT have back in those care-free days of razor blades and LetraSet Press-on Letters was…. GREY TEXT.

Did we ever use grey text? No, of course not. It would take a separate plate for grey ink since you can't half-tone a column of body text to make it grey!!, If someone in the layout room suggested grey text, they'd have been laughed out onto the street.

Today all you have to do is flick a couple hex values into CSS and presto, INSTANT BAD DESIGN CHOICE.

I don’t know about all of you, bu myself, GREY TEXT impedes my reading far more than a minor typographic choice of punctuation whitespace.

> _Briefly, my understanding is that:_
> * _In the days of typewriters with fixed-width font, the standard was two spaces after periods. (or, more accurately, after “terminal punctuation”, including periods and explanation marks and question marks)_

Yes, this was to make typewritten manuscripts easier to read and markup — it should be noted that they were ALSO double line spaced. Legal pleadings are STILL done this way (and probably forever shall, and on “pleading paper” which numbers each line) so the judge can make notes in the whitespace between lines.

> * _Variable width fonts, sophisticated kerning, and such made two spaces no longer needed for most readers to clearly distinguish the end of sentences._
> * _Once "desktop publishing" (DTP) made these common-place, professional publications went to single space after periods._

This was true way back when as well — Among typographers it was considered very bad form back in the day, as it still is now to do things like “double space.” Inside typography, hitting the space bar OR the return key twice in a row is considered “amateur,” in part because we have the means to adjust all of these things using typography tools, which have the distinct advantage that we can finely adjust and manipulate the type metrics later to specifically tune the leading, tracking, kerning, wrap, justify, margin, indent,  dropcap, etc etc — if there are errant double spaces lurking in the text then when we adjust we will have unexpected behavior.

CSS does not at present have this level of granular control. But worth adding to the list as a user custom feature.

But again, as I mentioned previous, space after period is built into a font as part of the kerning.

> Of course, there are some for whom two spaces after periods increases readability – including some with low vision who cannot easily see periods and some with certain cognitive disabilities. Thus, I would support extra space after periods being an option, and would oppose it being a suggested practice.

I agree it is a user custom layer, and I strongly agree that it is wrong to ever make the use of any form of double spacing “suggested practice.” though a CSS property would be good, along with a few others (like xheight access).


> (I also wonder about the priority of it. My initial feeling is that it is fairly low priority compared to other things needed to improve readability by people with cognitive, learning, and visual disabilities. Yet, I have not researched this particular point since about 1995. :-)

I have, it’s not a thing to be honest. There are other much bigger problems like GREY TEXT, zoom locks, reflow fail.

>> https://link.springer.com/article/10.3758/s13414-018-1527-6
> 
> _Quote: "It should be noted that the paragraphs used in the current experiment were presented in a monospaced fixed font.”_
> _Quote: “Inter-line spacing was quadruple…”_

Yea, not representative of reality — and it is well known in research that monospaced fonts generate substantially different reading speed results.

> _It is very good that they clearly stated the font and the line spacing. And, I think that makes the study nearly irrelevant for today’s text._

I agree.


> _(side note: I found it interesting that people who type one space had reading speeds of 85, 82, 78, 79; and people who type two spaces had reading speeds of 72, 70, 71, 74. That is quite a difference.)_

Actually those figures (in parenthesis) were not the reading speeds, those were the standard deviations. The difference in readings speeds are actually inconsequential.

### Those who use one space when they type:

- They read one spaced test at: 291 
- They read TWO spaced text at: 288


### Those who use two spaces when they type:

- They read one spaced test at: 305 
- They read TWO spaced text at: 314


SO: this indicated (every so slightly) that those accustomed to ONE space, read ONE space text faster, and those accustomed to TWO spaces reads two space text faster.

What this says to me is that our cognitive process WORKS BEST with what we are ACCUSTOMED TO. Which…. we already knew I think...

And don’t believe the GRAPHS in that research article — if you look at the bar graph, you’ll see it STARTS at 260, so it is severely weighting/over emphasizing the “gain” of the two spaced version!!! We are talking about a 1% to 3% difference, in other words NOISE with no clear statistical significance.

If fact, I don’t know how that and a few other things got past peer review. There were a lot of badly formatted tables and graphics in this paper… ?!?!




> _A little relevant background: I was a trained and professional technical writer and editor in the late '80s and early '90s – near the start of the DTP era. (yup, with my early Mac, PageMaker software, and LaserWriter printer ;-) At that time, there was a strong feeling in the DTP field that one space after period was the sign of a professional, and two spaces was the sign of an amateur or old school typewriter training._

I still miss Aldus Freehand.


> _Personally, whenever I get a document with two spaces after periods, it is one of the first things I customize – replace with one space. I cannot say how much of this is due to past indoctrination that it is amateurish, and how much is to improve readability and cognitive processing for me._

I use BBedit and regex to clean all the text files clients give me. Most clients hand in manuscripts with much greater travesties of style than an errant space, LOL...


Thanks for triggering my ancient memories, BTW…


Andy


> _OK, I've said enough for now. :-)_
> 
> _Best,_
> ~_Shawn_
 [1] rivers of white https://en.wikipedia.org/wiki/River_(typography)
