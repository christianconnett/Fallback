# Fallback

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
		@include margin(16, x, x, 16);
	```
	````css
	/* CSS */
		margin-top: 16px;
		margin-left: 16px;
		margin-top: 1rem;
		margin-left: 1rem;
	```

4. To convert rems within parenthesis you must interpolate.
	```scss
	// SCSS
		width: calc(25% - #{rem(16)});
	```
	```css
	/* CSS */
		width: calc(25% - 1rem);
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
	@include margin($top, $right, $bottom, $left);
		
### Margin
```scss
// SCSS
	@include margin(16, 16, x, x);
```
```css
/* CSS */
	margin-top: 16px;
	margin-top: 1rem
	margin-right: 16px;
	margin-right: 1rem;
```

### Padding
```scss
// SCSS
	@include padding(x, x, 16, 16);
```
```css
/* CSS */
	margin-bottom: 16px;
	margin-bottom: 1rem
	margin-left: 16px;
	margin-left: 1rem;
```

### Border-Width
```scss
// SCSS
	@include borderWidth(16, 16, x, x);
```
```css
/* CSS */
	border-width-top: 16px;
	border-width-top: 1rem
	border-width-right: 16px;
	border-width-right: 1rem;
```

etc...
