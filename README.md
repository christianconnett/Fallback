# Fallback v1.1

Fallback is a Sass partial of mixins and functions that convert rem units to pixel units and has partial shorthand support.



## General

1. ONLY use pixel units.

2. Exclude the px. It's appended automatically.
	```scss
	// SCSS
		@include rem(margin-top, 16);
	```
	```css
	/* CSS */
		margin-top: 16px;
		margin-top: 1rem;
	```

3. Use "x", without quotes, if you want to use shorthand, but don't want to redefine a value.
	```scss
	// SCSS
		@include remBlock(margin, 16, x, x, 16);
	```
	````css
	/* CSS */
		margin-top: 16px;
		margin-left: 16px;
		margin-top: 1rem;
		margin-left: 1rem;
	```

4. To convert rems within parenthesis using the function you must interpolate.
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
*Not to be used in stylesheets besides _fallback.scss*
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
```scss
// SCSS
	@include remBlock(margin, 16, 16, x, x);
```
```css
/* CSS */
	margin-top: 16px;
	margin-top: 1rem
	margin-right: 16px;
	margin-right: 1rem;
```
