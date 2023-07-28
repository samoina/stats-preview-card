# Frontend Mentor - Stats preview card component solution

This is a solution to the [Stats preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/stats-preview-card-component-8JqbgoU62). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
    - [How to add an overlay](#how-to-add-an-overlay)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size

### Links

- Solution URL: [Github Repo](https://github.com/samoina/stats-preview-card)
- Live Site URL: [Netlify Link](https://samoina-stats-preview-card.netlify.app/)

## My process

### Built with

- Semantic HTML5 markup
- CSS
- Flexbox
- Mobile-first workflow

### What I learned

#### How to add an overlay

I learned how to add the purple overlay over the image. Here's how I went about it:

1. I used the ::before pseudoselector to create an 'extra' layer on top of the existing image.
2. I positioned the parent container relative to create a new reference position for its children. this way, the children will be placed relative to the parent and NOT the document, thus not affecting other elements.
3. I then added some style to the pseudoselector with top, left, width and height to cover the image entirely, before adding a background color to it.
4. I then used the `mix-blend-mode` which determines how the image color blends with the overlay, then set the opacity to determine the transparency.

```html
<picture class="main__picture">
	<!-- Image source when screen is wider than 375px -->
	<source
		media="(min-width: 375px)"
		srcset="images/image-header-desktop.jpg"
		sizes=""
	/>
	<!-- Default image source for mobile responsive -->
	<img src="images/image-header-mobile.jpg" alt="background image" />
</picture>
```

```css
/* Create the purple overlay */
.main__picture {
	position: relative;
}

.main__picture ::before {
	content: '';
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background-color: var(--soft-violet);
	mix-blend-mode: multiply;
	opacity: 0.5;
}
```

### Useful resources

- [CSS mix-blend-mode](https://developer.mozilla.org/en-US/docs/Web/CSS/mix-blend-mode) - This helped me better understand how to blend the image colors with that of the overlay

## Author

- Website - [Samoina Lives](https://samoinalives.wordpress.com/)
- Frontend Mentor - [@samoina](https://www.frontendmentor.io/profile/samoina)
- Twitter - [@samoina](https://www.twitter.com/samoina)
