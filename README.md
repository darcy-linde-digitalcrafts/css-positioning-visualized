# Positioning Visualized

Open this demo in the browser and look at the code side-by-side.

Let's approach the positions in the order they appear in the HTML:

## Static

The static box is the easiest to understand.
The position of the static box has not been offset in any direction and the box
remains in the default position - the top left corner of its parent element. We
can even observe that the borders between the static box and the parent
container are touching.

## Fixed

In fixed positioning, the element is removed from the document flow and remains
"fixed in place", even when the screen is scrolled in the browser viewport.
Scroll the browser screen up and down and see how the fixed box remains
stationary.

## Relative

Relative positioning allows an element to be moved from its original position
relative to its normal position in the document flow. It does not take the
element out of the normal flow of the document, meaning that other elements on
the page are still positioned as if the relatively positioned element were in
its original position.

In this case, we moved the relative box 20px from the top and left sides of its
parent container.

## Absolute

Absolute positioning, as opposed to relative positioning, takes the element out
of the normal flow of the document and positions it relative to its first
parent non-static element. If no ancestor elements have a position value other
than static (which is the default), the element will be positioned relative to
the &lt;body&gt; element. Absolute positioning allows you to precisely place an
element anywhere on the page, and it can overlap other elements.

Here the absolute box is removed from the normal flow which is why it is not in
the parent box you may expect it to reside in. There is no ancestor with a set
position value either, which is why the absolute box is relative to the
&lt;body&gt; element. The box is offset by 100px in each direction as to not
conflict with other examples in the document.

## Sticky

Sticky positioning combines features of relative and fixed positioning.

Consider
[this definition](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
from MDN:

> The element is positioned according to the normal flow of the document, and
> then offset relative to its nearest scrolling ancestor and containing block
> (nearest block-level ancestor), including table-related elements, based on the
> values of top, right, bottom, and left. The offset does not affect the
> position of any other elements.\
> This value always creates a new stacking context. Note that a sticky element
> "sticks" to its nearest ancestor that has a "scrolling mechanism" (created
> when overflow is hidden, scroll, auto, or overlay), even if that ancestor
> isn't the nearest actually scrolling ancestor.

With this in mind, let's consider where the sticky element is residing in
relation to the css offset we gave it. The element initially displays relative
to where it would be rendered in normal flow. This means that it starts by
being displayed in that same position as the static position - and this can be
confirmed by removing the css top and left properties. By setting `top: 0`, the
sticky box is "stuck" at the 0px mark even when attempting to scroll past it.
However, the sticky box is still kept within the parent container and can't
move past the container, even when we scroll past it.
