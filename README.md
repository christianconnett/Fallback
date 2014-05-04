# Fallback v1.4.1
Fallback is currently a single Sass mixin with a couple small functions that convert rem units to pixel units. Oh, and it does it with shorthand code unlike other rem to px Sass mixins.


## Rules and Stuff
1. Only use pixel units. Not rems.

2. Don't include the px. The px is appended automatically.
	```scss
	// SCSS
		@include rem(margin, 16);
	```
	```css
	/* CSS */
		margin: 16px;
		margin: 1rem;
	```

3. You can use shorthand!
	```scss
	// SCSS
		@include rem(margin, 2 4 8 16);
	```
	````css
	/* CSS */
		margin-top: 2px;
		margin-top: 0.125rem;
		margin-right: 4px;
		margin-right: 0.25rem;
		margin-bottom: 8px;
		margin-bottom: 0.5rem;
		margin-left: 16px;
		margin-left: 1rem;
	```

4. Use x to skip a value you don't want to re-define.
	```scss
	// SCSS
		@include rem(margin, 16 x x 16);
	```
	````css
	/* CSS */
		margin-top: 16px;
		margin-top: 1rem;
		margin-left: 16px;
		margin-left: 1rem;
	```

5. To convert rems within parenthesis, you must use the rem function and interpolate. This is purely to be used if you're too lazy to do math because you must manually specify a fallback.
	```scss
	// SCSS
		width: calc(25% - 16px);
		width: calc(25% - #{rem(16)});
	```
	```css
	/* CSS */
		width: calc(25% - 16px);
		width: calc(25% - 1rem);
	```

6. You can use shorthand for the position property.
	```scss
	// SCSS
		@include rem(position, 2 4 8 16);
	```
	````css
	/* CSS */
		top: 2px;
		top: 0.125rem;
		right: 4px;
		right: 0.25rem;
		bottom: 8px;
		bottom: 0.5rem;
		left: 16px;
		left: 1rem;
	```

7. You can make things important. Don't include the !. It's appended automatically.
	```scss
	// SCSS
		@include rem(margin, 16 x x 16, important);
	```
	````css
	/* CSS */
		margin-top: 16px !important;
		margin-top: 1rem !important;
		margin-left: 16px !important;
		margin-left: 1rem !important;
	```


## To-do
+ Compile CSS shorthand when possible
+ Automate browser prefixes for CSS3

## Changelog
+ v1.4.1
	+ Fixed important not being applied
+ v1.4
	+ Generally made things more awesome
	+ Simplified syntax
	+ Combined rem and remBlock mixins
	+ Added important support
	+ Removed size and translate mixins (might add back in a future version)
+ v1.3
	+ Added optional auguments for remBlock
	+ Added multiple vaules for auguments, though, not very useful just yet
+ v1.2
	+ Merged translate2d and translate3d mixins
+ v1.1
	+ Added remBlock to replace simmilar mixins
+ v1.0
	+ Initial Release