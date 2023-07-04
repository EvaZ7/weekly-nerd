# Pre-CSS day 🎊

Weekly nerds

---

## Building a website like it’s 1999

> Sophie Koonin
> 

Let’s bring back the weird!!!

### First

- They are covered in animated gifs
- Now there are CSS animations etc etc.
- It’s not a great idea to put an gif with wild animations in a `<img>`, users have different preferences
    - Prefers reduced motion on img
- `<blink>` in HTML tag is also not very accessible for some users so use word art instead
    - `background-clip: text;`
    - Background: clip tot text, so use an container for shadows because
    - `Perspective-origin: bottom center;` ← for awsome text shadows and style it further with `::before`
- Music on websites on autoplay is `<audio aria-label=”play music”></audio>`.….
- DHTML cursor trail window.Matchmedia
- [webmention.io](http://webmention.io)
- **Bridgy** lets you know when your website is mentioned on social media

---

## Keep CSS weird

> Adam Argyle
> 

- LCH == new color-space
    - L has been moddeled around human preception
    - The amount of lightness is the same in this color space compared to an HSL color space
    - From light to dark:
    
    ```css
    --swatch-1: oklch(99% 0.5 var(--hue));
    --swatch-2: oklch(89% 0.5 var(--hue));
    --swatch-3: oklch(79% 0.5 var(--hue));
    --swatch-4: oklch(69% 0.5 var(--hue));
    --swatch-5: oklch(59% 0.5 var(--hue));
    --swatch-6: oklch(49% 0.5 var(--hue));
    ```
    
    - Gradient:
    
    ```css
    --hue: 0;
    
    --swatch-1: oklch(99% .05 var(--hue));
    --swatch-2: oklch(89% .1 var(--hue));
    --swatch-3: oklch(79% .15 var(--hue));
    --swatch-4: oklch(69% .2 var(--hue));
    --swatch-5: oklch(59% .25 var(--hue));
    --swatch-6: oklch(49% .3 var(--hue));
    ```
    
    - Changing values:
    
    ```css
    --hue: 250;
    
    --text-1: var(--swatch-6);
    --text-2: var(--swatch-7);
    ```
    
    [gradient.style](http://gradient.style) 
    
    ---
    
    ## Debugging CSS with chromedevtools
    
    > Chang haohan
    > 
    
- Tooling should have good UX as well
- Debug UI-related issues
- Why CSS debugging is important
    - Specificity is hard to follow
- New:
    - CSS authoring hints: helps identify …
    - CSS specificity hints: determine the order of applied CSS rules (gives number of specificity)
- Colors: there are new color spaces coming!!! to devtools so you can switch between them
- Animation: being able to edit the cubic bezier in the devtools (transition: linear(0%,2%))
- Container queries: See the current container size
- Scroll driven animations: animation-range: