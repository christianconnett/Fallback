Fallback
========

Fallback is a Sass partial of mixins and functions that convert rem units to pixel units and has partial shorthand support.



Some rules and info
========

[] ONLY use pixel units.


[] Exclude the px. It's appended automatically.
	input:
		@include rem(margin-top, 16);

	output:
		margin-top: 16px;
		margin-top: 1rem;


[] Use "x", without quotes, if you want to use shorthand, but don't want to redefine a value.
	input:
		@include margin(16, x, x, 16);

	output:
		margin-top: 16px;
		margin-left: 16px;
		margin-top: 1rem;
		margin-left: 1rem;


[] To convert rems within parenthesis you must interpolate.
	input:
		width: calc(25% - #{rem(16)});

	output:
		width: calc(25% - 1rem);
