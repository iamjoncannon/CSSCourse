
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







