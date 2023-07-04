# CSS-day!

Created: June 9, 2023
Reviewed: No

# Container queries

> Miriam Suzanne
> 

- Intrinsic: webdesign using intrinsic size of elements
- Mediaqueries become a little bit obsolete
- Containers DO. know stuff!!
- From @media to @container

Infinite layout loops?

__**we can’t style the container we want to query___**

```css
Overflow-wrap: break-word;
```

### Contain: inline size

problems:

- jumping content
- contain: block-size just doesn’t work
- Only measure the axes we contain
- Use size containment with overflow

```css
contain: layout;
```

we only create containers explicitly 

- There is no default for container
- Make sure the html is set to the full vh
- @Container  can have multiple values
- @Container changes based on the font-size is different than @media
- html container: layout root / size;

```css
html {
container: layout root/size;
}
```

Finding containers:

For matched element find the nearest ancestor thats has container names/types

- Containers cant self-query! -nest however you want to
- Each one is always measuring an element

@container for custom properties and styling!!!!!

no containment required 

there are lot of things to measure with state query of containers

---

## Tooling and workflows

> Umar Hansa
> 

### CSS snippets

- Configure user snippets (turn on in setting)
    - Co-pilot 2.0
- Get the code you need fast with pre-defined values
- Alfred snippets
- Go to snippet tools

### AI stuff

- bloop: type out your code in words (chat gpt for code)
- Github copilot chat, with interactive editor
- Write CSS with voice?! copilot voice works pretty well but is pretty error sensitive
- Whisper/macwhisper

### Other stuff

- command shift p in VScode to activate
- expand region: command and quote
- live preview
- your editor everywhere: ghostText
- Jump to destination: jumpy/acejump, command ;

### Devtools

- sync CSS changes: styles pane , experiments:
- Local overwrite
- Filesystem: add folder to workspace: sync css with devtools: command and S

### Keyboard workflow

- Scoot:shortcat:wooshy

### Css performance tooling

- CSS coverage: await [page.click](http://page.click) (’[aria -label=”Main Menu”]’)
- Lighthouse: npx lighthouse http:// —view, run it in command line!
    - npx lhci server
    - npx lhci autorun \ http://
    - Details in github takes you to lighthouse then

### Visual testing

- visual testing: catch bugs before your user does
- DIY with playwright
- Visual testing dashboard (wikipedia has an open source one)
- Wikimedia/pixel
- Applitools: paid but free tier

---

## Building components

> Stephanie Eckles
> 

### Css resets

```css
a:not([class]) {
text-decoration-thickness: max()
}
```

:focus-visible: 

```css
:focus-visible {
/*standard focus styles*/
}
```

```css
:target {
scroll-padding-block-start: 2rem;
}
:focus {
scroll-padding-block-end: 8vh;
}
```

### Project architecture

- Css nesting!!!
    - Key differences:
        - must begin with symbol, you cant just begin with an element
        - allows selectors for pseudo classes
- @layer
    - initial order defines the applied priority order
    - Less nested styles have priority over nested styles
    - You can use @layer theme (in this put :root)
- :is is the elements self an h2 or anything else
- :focus-within, check of an child within the parent has an focus state
- @container grid-item (inline-size > 40ch){}
- @container layout-container (inline-size > 70ch){}
- Aspect ratio is forgiving it is a little bit responsive
    - max-inline-size: 100%
- text-wrap: balance; does not change the actual with
- .container:has(li:nth-of-child(11))

---

## Creative coding

> Jhey Tompkins
> 

- .form-group:has(:valid) .char {}
- :root:has(.theme-toggle)
- :root:has([value=theme]){}

### Css anchoring

- bottom: anchor(— anchor top) anchor-name: anchor;
- div between two anchor pieces
- You can anchor pieces together

make your menu a popover!!!

### Scroll driven animations

- animation-timeline: scroll;
- animation-timeline: view;
- scrolling content reveals!

---

## Styling web components (shining light on the shadow DOM)

> Cassondra Roberts (Adobe)
> 

- window.customElements.define(”the-card”, Card)
- Custom build-in vs autonomous
- assign semantic styles to semantic DOM
- Styles based on state don’t need their own classes
- fancy div
- ::slotted slot

---

## Scroll-driven animations and view transitions

> Bramus van Damme
> 

- be mindfull of your user, prefers reduced motion
- document.startViewTransition in js
    - :root {view-transition-name: root;} in css
- enter and exit only transitions
- full page transitions :  —webkit-mask-image: linear gradient;
- directional transitions: $root.add(direction) and remove it again left-to-right

### view transition

- <meta name=”view-transition” content=”same-origin”/>

### Scroll driven animations

- scroll: api
- animation-timeline: scroll(<axis><scroller>)
    - animation+ animation-timeline
    - drop duration + drop timeline + done
    - animation-range: 0 90vh;

### View timeline

- animation-timeline: view(nearest inline);
- animate image, track li item
- scroll driven animation tool
- entry can be put in keyframes and exit also

- scroll driven vs scroll triggered

---

## Structuring and restructuring

> Manuel Matuzovic
> 

- Use more in custom properties for different things
- scrollbar-gutter: stable;
-