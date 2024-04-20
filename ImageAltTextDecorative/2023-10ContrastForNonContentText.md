## October 31, 2023
# From: Contrast Requirements for Non-Content Text
[_Incidental and Noninteractive Text (WCAG2)_](https://github.com/w3c/wcag/issues/3418#issuecomment-1787523709)

> ..._WCAG 2 contrast minimum does not appear to cover how one should consider non-interactive and incidental text_...
The uses of text and the user needs for text are among the widest spectrums in terms of variation and what is best practice. WCAG 2.x SCs provide only sparse guidance here, partly by design to keep the SCs simple and testable in a binary way.

> ..._Examples of this sort of text could be because certain information in a product's dashboard has been dimmed due to irrelevance to the user's current content settings_...

Arguably this stated example falls under "inactive component", and in that case related WCAG 2.x SCs essentially absolve the content author of any specific level of contrast. 

Taking a look at SC 1.4.3 (emphasis added):

> - Text or images of text that are part of an **_inactive_** user interface **_component_**, that are pure decoration, **_that are not visible to anyone_**, or that are part of a picture that contains significant other visual content, have no contrast requirement.

The "not visible to anyone" is one part of this that also addresses most of the examples you mention, in association with the inactive components clause. The non-foreground parts of a carousel, the dimmed text behind a modal, the fade-out preview text. All of these embody the "not visible to anyone" basis. But they are also all under user control: clicking to advance the carousel, clicking the modal, or buying a subscription.

The "normative" part of the SCs is what is in the SC itself. In the case of the carousel, the frame in view is the active frame, the others, partially obscured are _inactive user interface components_. This is true of the modal, when the modal is up front, blocking view, the modal is active and the blocked view is an _inactive user interface component_, and so is the text fading away.

Keep in mind that WCAG 2.x was designed/structured to be testable in a very binary way, and therefore must be simple. From a legal point of view, an element is either the foreground content to view (active) or it is background/ancillary (inactive). To be testable the way WCAG 2.x is written and structured, everything is essentially a binary pass/fail, these "gradient" examples notwithstanding.

It would be unreasonable to say that something **_has to_** cut off and can not fade out. **The fade itself has meaning**, and in the case of preview text fading out, the meaning is "hey you wanna read? You gonna pay!". The start of the dimming or fade out is the start of where it becomes an "inactive" component.

This is one of the topics we're working on for WCAG 3, which led to [text use cases](https://github.com/Myndex/SAPC-APCA/discussions/39). In the present case of content that is intentionally suppressed, it would be categorized as either ["sub-fluent"](https://readtech.org/ARC/tests/visual-readability-contrast/?tn=conform#sub-fluent) or ["non-fluent"](https://readtech.org/ARC/tests/visual-readability-contrast/?tn=conform#non-fluent). This is all an open discussion at the [readability forum on GitHub](https://github.com/Myndex/SAPC-APCA/discussions/) you're welcome to discuss ways to handle these nuances.


> ..._it should meet the non-text contrast requirement_...

In order to make such fine distinctions, the contrast metric used needs to be perceptually uniform, and WCAG 2.x contrast is not at all uniform, and therefore not fit for such a purpose.

While I agree there should be standards for semi-suppressed content, WCAG 2.x contrast math is a blunt instrument that's only useable within a narrow range where the background is very light. 1.4.11 itself has no empirical support, and does not apply here in any case.
