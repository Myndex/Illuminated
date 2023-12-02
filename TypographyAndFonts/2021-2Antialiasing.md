Thank you for commenting Ram @RamNathaniel 

### This is a well understood behavior
**And is already compensated for by the APCA math and lookup tables**, and is also discussed in the specification at least to some degree.

The new APCA math and minimum font size and weight tables already take this into account in a way the old WCAG 2.x contrast did not.

Among other things, the specification indicates that _"-webkit-font-smoothing: antialiased"_ is prohibited for thin fonts (only default sub-pixel anti-aliasing is allowed or contrast must be increased by 30 or font stroke width no less than 2.5px if the blur-type font smoothing is used). 

Also, the specification is designed around the standard (100%) zoom level, on a minimum resolution screen, and is further based on multiple psychophysical studies on readability (Lovie-Kitchin, Legge, Arditi, et.al.)

Most of the highly technical information such as you are mentioning was removed from the actual written standard (to which I objected), but is nevertheless going to be placed into a white paper. Some of the pre-white paper information is here: https://www.w3.org/WAI/GL/task-forces/silver/wiki/Visual_Contrast_of_Text_Subgroup/Whitepaper


Thank you for your comments,

Andy


_Andrew Somers_
_W3 AGWG Invited Expert_
_Myndex Color Science Researcher_
_Inventor of APCA contrast_

See also: https://github.com/Myndex/SAPC-APCA
