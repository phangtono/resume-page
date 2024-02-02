# I'm still learning - Resume Page.

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
- [Learning From](#learning-from)

## Overview

### Screenshot

![](./screenshot_1.png)

![](./screenshot_2.png)

### Links

- Solution URL: [resume-page-code]()
- Live Site URL: [resume-page-live-site]()

### Built with

- HTML5
- CSS
- Flexbox
- Grid
- Accessibility

### What I learned

The website was built following the rules of accessibility.

```html
    <h2 class="visually-hidden">My Skill</h2>
```

For layout, use a grid. grid-template-columns, grid-column, and grid-auto-flow: dense so that the aside can fill empty positions.

```css
.main-grid{
    --_side_width: clamp(7.5rem, 20vw, 15rem);
    --_main_width: 1fr; 
    --_gap-size: 10vw;

    display: grid;
    grid-template-columns: var(--_side_width) var(--_main_width) ;
    gap: var(--_gap-size);
    grid-auto-flow: dense;
    align-items: center;
    min-height: 100vh;
    min-height: 100dvh;
}

main{
    padding-block: 2rem;
    grid-column: 2;
    width: calc(100vw - var(--_side_width) - var(--_gap-size));
}

aside{
    grid-column: 1;
    align-self: stretch;
    display: flex;
    justify-content: center;
}
```

For the list icon, use grid, border-left as a line, in li::after, border-radius to create a round dot, outline as a shadow

```css
.icon-list {
    list-style: none;
    display: grid;
    align-content: center;
    gap: 3rem;
    border-left: 1px solid var(--clr-primary-300);
    padding: 0;
    margin: 0;
    /* margin-left: clamp(3rem, 10vw, 10rem); */
    height: 100%;
}

.icon-list > li {
    position: relative;
    padding-left: 3rem;
}

.icon-list > li::after {
    --_size: .5rem;
    position: absolute;
    content: "";
    top: 0;
    left: calc(var(--_size) / -2);
    width: var(--_size);
    aspect-ratio: 1;
    outline: .5rem solid var(--clr-primary-400);
    border-radius: 50%;
    background: var(--clr-neutral-100);
}

```

For , use the grid. so that the scrollbar appears automatically overflow-x: auto. to have space use job-experience::after, width: 50px; background: transparent, and use webkit-scrollbar to style the scrollbar outside of Firefox

```css
.job-experience{
    display: grid;
    justify-content: start;
    grid-auto-flow: column;
    gap: 1rem;
    overflow-x: auto;
    padding-block: 2rem;

    /* scrollbar for firefox */
    scrollbar-color: var(--clr-accent-400) var(--clr-primary-400);

    position: relative;
}

.job-experience::-webkit-scrollbar{
    height: .75rem;
}

.job-experience::-webkit-scrollbar-track{
    background-color: var(--clr-primary-400);
    border-radius: 100vw;
}

.job-experience::-webkit-scrollbar-thumb{
    background-color: var(--clr-accent-400);
    border-radius: 100vw;
}

.job-experience::after{
    content: '';
    width: 50px;
    background: transparent
}
```

## Learning From :

- Kevin Powell - [Kevin Powell](https://www.youtube.com/watch?v=LkZPd0oRlMQ&list=WL&index=46)"# resume-page" 
