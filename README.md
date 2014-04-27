# Fallback

Fallback is a Sass partial of mixins and functions that convert rem units to pixel units and has partial shorthand support.



## Using Fallback:

1. ONLY use pixel units.

2. Exclude the px. It's appended automatically.
	+ scss:
	```scss
		@include rem(margin-top, 16);
	```
	+ css:
	```css
		margin-top: 16px;
		margin-top: 1rem;
	```

3. Use "x", without quotes, if you want to use shorthand, but don't want to redefine a value.
	+ scss:
	```scss
		@include margin(16, x, x, 16);
	```
	+ css:
	````css
		margin-top: 16px;
		margin-left: 16px;
		margin-top: 1rem;
		margin-left: 1rem;
	```

4. To convert rems within parenthesis you must interpolate.
	+ scss:
	```scss
	input:
		width: calc(25% - #{rem(16)});
	```
	+ css:
	```css
		width: calc(25% - 1rem);
	```
