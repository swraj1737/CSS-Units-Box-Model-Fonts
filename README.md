# Task 3 – Viewport Units, Box Model, and Styling Notes

This little page was built while learning about how the size of the browser window affects layout and how the CSS box model works. I wanted to make something that stayed inside the viewport no matter what screen I opened it on, and the process taught me a few things.

The design is trivial: a centered box containing an image and a button. Everything except the box itself is sized using `vh` and `vw`. Those units are tied directly to the viewport height and width, so as you shrink or grow the window, the elements scale proportionally. That makes it easy to guarantee the entire page fits exactly in the screen — I just made the container 90 vh tall and the button 10 vh tall, and then used flexbox to centre the container. No matter what size the browser is, the image plus button always sum to 100 vh and the page never scrolls.

I also reset the default margins and padding on every element and set `box-sizing: border-box` at the top of the stylesheet. With that rule in place, the width and height of an element include any padding or border, which means I can add spacing or outlines without accidentally pushing the element larger than the viewport. It’s a small thing, but it makes layout calculations much more predictable once you start using viewport units.

To make the button look a bit nicer, I added a hover effect that changes its colour gradient, scales it up slightly, and gives it a subtle drop shadow. I also loaded a Google Font (`Poppins`) so the text isn’t just the default system font. That was mostly to show I know how to include external typefaces and pick something a little more friendly than the default.

### What I learned

* **Viewport units** are great for responsive spacing; `10vh` means 10 % of the visible height, so I don’t have to worry about hard‑coding pixel values.
* **Box model reset** with `box-sizing: border-box` removes a lot of the mystery when sizing elements.
* Combining the two makes it trivial to build a layout that never causes vertical scrollbars, as long as I make sure the sum of my container and its children equals 100 vh.
* A simple transition on a button can make it feel much more interactive.

### Running the project

Just open `index.html` in any modern browser. No build steps or tools are necessary. The page should fill the window without any scrollbars and the button hover state is the only interactive part.

That’s it – a small exercise, but it helped cement some core CSS concepts in my head.
