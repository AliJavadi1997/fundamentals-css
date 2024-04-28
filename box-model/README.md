# Box Model Study

### Margin is unique

    it doesn’t affect the size of the box itself per se, but it affects other content interacting with the box, and thus an important part of the CSS box model.

    The size of box itself is calculating like this:
        width = width + padding-left + padding-right + border-left + border-right
        hight = height + padding-top + padding-bottom + border-top + border-bottom

### What if these values are undeclared?

    If padding or borders are undeclared, they are either zero.

### Default width of block level boxes?

    If you don’t declare a width, and the box has static or relative positioning, the width will remain 100% in width and the padding and border will push inwards instead of outward. But if you explicitly set the width of the box to be 100%, the padding will push the box outward as normal.

    The key: Width = "whatever is left"

### Absolute Boxes with No Width

    Their width is only as wide as it needs to be to hold the content.So if the box contains a single word, the box is only as wide as that word renders. If it grows to two words, it’ll grow that wide.
    This should continue until the box is 100% of the parent’s width (the nearest parent with relative positioning, or browser window) and then begin to wrap.

    **Warning** there are plenty difference between how browsers render and handle the absolute boxes width.

### Floted Boxes with No Width

    Floated elements with no width will size themselves to fit their content, but not wider than their parent element.
    **Warning** This behavior can be unreliable for overall page layout, so it's better to set explicit widths for floated elements.

### Inline Elements are Boxes Too
    Think of them as really really long and skinny rectangles, that just so happen to wrap at every line.
    The wrapping is what makes it confusing. left margin is only apply on the first line but the padding will apply blow and above the lines.


