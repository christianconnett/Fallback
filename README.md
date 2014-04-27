# Fallback v1.2

Fallback is a Sass partial of mixins and functions that converts rem units to pixel units and adds more shorthand.



## General

1. Only use pixel units.

2. The px is appended automatically.
	```scss
	// SCSS
		@include rem(margin-top, 16);
	```
	```css
	/* CSS */
		margin-top: 16px;
		margin-top: 1rem;
	```

3. You can use shorthand.
	```scss
	// SCSS
		@include remBlock(margin, 16, 16, 16, 16);
	```
	````css
	/* CSS */
		margin-top: 16px;
		margin-top: 1rem;
		margin-right: 16px;
		margin-right: 1rem;
		margin-bottom: 16px;
		margin-bottom: 1rem;
		margin-left: 16px;
		margin-left: 1rem;
	```

4. Use x to skip a value.
	```scss
	// SCSS
		@include remBlock(margin, 16, x, x, 16);
	```
	````css
	/* CSS */
		margin-top: 16px;
		margin-top: 1rem;
		margin-left: 16px;
		margin-left: 1rem;
	```

5. To convert rems within parenthesis, you must use the rem function and interpolate.
	```scss
	// SCSS
		width: calc(25% - #{rem(16)});
	```
	```css
	/* CSS */
		width: calc(25% - 1rem);
	```

## Functions
### Rem
```scss
// SCSS
	width: #{rem(16)};
```
```css
/* CSS */
	width: 1rem;
```
### Px
*Not For Use*
```scss
// SCSS
	width: #{px(16)};
```
```css
/* CSS */
	width: 16px;
```

## Mixins
### Rem
Supports all properties with a single unit value.
```scss
// SCSS
	@include rem(max-width, 16);
```
```css
/* CSS */
	max-width: 16px;
	max-width: 1rem;
```

### Size
Shorthand for width and height.
```scss
// SCSS
	@include size(16, 16);
```
```css
/* CSS */
	width: 16px;
	width: 1rem;
	height: 16px;
	width: 1rem;
```
		
### Rem Block
Shorthand for all properies with 4 unit values.
Adds support for position.
```scss
// SCSS
	@include remBlock(margin, 16, 16, x, x);
	@include remBlock(position, 16, 16, x, x);
	position: relative;
```
```css
/* CSS */
	margin-top: 16px;
	margin-top: 1rem
	margin-right: 16px;
	margin-right: 1rem;
	top: 16px;
	top: 1rem
	right: 16px;
	right: 1rem;
```

### Translate
If only two plains are desired, just use an x on the z variable.
```scss
// SCSS
	@include translate(16, 16, x);
```
```css
/* CSS */
	transform: translateX(16px);
	transform: translateX(1rem);
	transform: translateY(16px);
	transform: translateY(1rem);
```