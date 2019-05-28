
### Three principles of CSS-

responsive design
writing maintainable and scalable code
web performance


### CSS architecture

think - build - architect

think about layout before writing code

build in HTML/CSS with consistent structure

create logical CSS architecture

think:

	component driven design- divide page into modular components- building blocks- reusable across project - independent, don't depend on parent element

	atomic design philosophy

build:
	
	naming classes- BEM- block element modifier
	block- standalone element that is meaningful on its own
	element- part of a block that has no standalone meaning
	modifier- different version of a block or element

```CS
.block {

}

.recipe {

}

.block_element {

}

.recipe_btn {

}

.block_element--modifier{

}

.recipe_btn--round {

}
```

people don't like it becuse its ugly, annoying to write

architect:

	create logical file structure
	7-1 pattern- 7 different folder, put partial SASS file, then one main file

	7: base, components, layout, pages, themes, abstracts, vendors

# NPM and Sass

## what is SASS

CSS preprocessor- makes CSS easier to organize- larger projects are impossible to navigate

write SASS- compiles into CSS

variables- reusable values for font sizes, spacing etc

nesting- nest selectors inside each other

operations- math

partials/imports- 

mixins- write reusable pieces of CSS code

functoins- produce value from calculation/computaiton/operation etc

extends- make different selectors inherit declarations

control directives- conditionals/loops (not generally in use )

SASS syntax- SCSS syntax (preserves CSS syntax)

# Natours Notes

anything that needs a media query should be defined in rem- relative to the root font size- default element base font size (defined on HTML tag) 

float- places an element on left or right of its parent container, allows elements to wrap around it. break's 'normal flow' of parent container, element is taken out of flow

use the inspector with the style box to play with parameters inside chrome

emmet- 

set dimensions of column layout beforehand

the 62.5% trick

box-shadow: x y blur color

transform- animation

transition: 2s - defines parameters for animation transition times

make an element opaque without making the children opaque:
background-color: rgba($color-black, .8)

background image- linear-gradient

background-blend - blending different 

clip-path- 

text-transform- uppercase/lowercase

text-align- center/right

box-decoration break- text blocks treated like separate elements (clone)

all elements except last: 

&:not(:last-child) {
	
}

margin 0 auto - center element inside another element

border-radius - round the element - in px

shape-outside - used in conjunction with float, defines how the elements outside curve around it

transform translate- move elements around relative to their relative position

images always need width- 100% width or height

he skewed the parent in one direction, then reskewed the child in the opposite direction

& > * {
	all child elements
}

can't have two transform functions- one on parent and in child - would have to put transform as value in the child's transform function

backface-visibility- 

video element-


<video class='class' autoplay muted loop>
	<source src='img/video.mp4'>
	<source src='img/video.webm'>
		browser not supported
</video>

object-fit: cover - fill entire parent while maintaining its aspect ratio

overflow: hidden - stops child element from expanding beyond parent

main and footer element tags

## navbar

"checkbox hack"

label connected to a hidden checkbox

input type='checkbox'

then a label 

position: fixed; like absolute except it never changes

background-image: radial-gradient

mixin to center an element in its parent:

position: absolute;
top: 50%;
left: 50%;
transform: translate(-50%,-50%)

inline-block: Compared to display: block, the major difference is that display: inline-block does not add a line-break after the element, so the element can sit next to other elements.

to hide elements, make opacity AND width 0

so, checkbox hack: 

"checked" pseudoclass 

```sass
&__checkbox:checked ~ &__background{
	transform...
}
```

~ is a general sibling selector - any sibling that matches

## popup in pure CSS

a popup container with an .8 transparent opacity and then the content inside with total opacity

background-color: rgba($color-black, .8)

child: 

background-color: rgba($color-white)

content- two images and text beside it

image		content box

image


to get the images to be the same height as the text content:

parent 
display: table

children
display: table-cell;
vertical-align: middle;

to toggle if its displayed, have the anchor direct to it as an id: href='#popup'

and the pop up contianer: id='popup'

.popup {
	
	opacity: 0;
	visiibility: hidden;

	&:target { // becomes the target
		opacity: 1;
		visibility: visible;
	}
}

# responsive design strategies

mobile or desktop first 

max-width or min-width queries

desktop first:

max-width- maximum width at which the query applies, after that, it stops working, overrides global CSS codes- stripping out elements that don't belong in larger screens

media queries are always done at the end- don't add importance or specificity, so they rely on the code order 

mobile first approach:

min-width:  minimum width at which the query applies

adding in elements as the screen sizes get larger

selecting breakpoints:

bad- selecting based on product sizes - this is bad because 

good - group based on popular device sizes - group 

perfect- ignore devices and look at content/design, put breakpoints when design breaks down

four breakpoints:

phone only: < 600px

tablet portrait: 600-900px

tablet landscape: 900-1200px

desktop: 1200-1800px

big desktop: > 1800px (not mandatory)

## mixins with media queries

media query manager

```cs
@mixin respond-phone { 
	@media (max-width: 600px){
		@content
	};
}

// inside selector

@include respond-phone {
	font-size: 50%;
}

```

better version:
"media query manager"

```cs
@mixin respond($breakpoint) {
	@if $breakpoint == phone {
		@media (max-width: 600px){
			@content
		};
	} 
	@if $breakpoint == tap-port {
		@media (max-width: 900px){
			@content
		};
	} 
	@if $breakpoint == tab-land {
		@media (max-width: 1200px){
			@content
		};
	} 
	@if $breakpoint == desktop {
		@media (min-width: 1800px){
			@content
		};
	} 
}

@include resopnd(phone){
	font-size: 50%
}

```

yada yada yada - best thing to use in media queries is em's (just know theres a reason)

converted to ems (final version)


```cs
@mixin respond($breakpoint) {
	@if $breakpoint == phone {
		@media (max-width: 37.5em){
			@content
		};
	} 
	@if $breakpoint == tap-port {
		@media (max-width: 56.2em){
			@content
		};
	} 
	@if $breakpoint == tab-land {
		@media (max-width: 75em){
			@content
		};
	} 
	@if $breakpoint == desktop {
		@media (min-width: 112.5em){
			@content
		};
	} 
}

// use:

@include resopnd(phone){
	font-size: 50%
}

```








