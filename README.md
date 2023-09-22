# bendable
Fluid &amp; responsive type scales with composable CSS utilities. See the [blog post for a more in-depth exploration of the type scaling mechanism](https://tobiasahlin.com/blog/responsive-fluid-css-type-scales/).

## Installation

Download `bendable.css`, or run:

```
npm install bendable
```

## Usage

To create a header that scales from the minimum size to the max size in the type scale, between the smallest and largest supported viewports, add the `font-1` and `5xl:font-14` classes:

```html
<h1 class="font-1 5xl:font-14">Scale all the things</h1>
```

This example introduces two concepts: minimum values (`font-x`) and font size **targets** (`viewport:font-x`). A target font size is a font size that will cause the size to scale smoothly from the smaller viewport towards its target at the larger viewport. In bendable, however, both **breakpoints** and **targets** exist as distinct mechanisms, where breakpoints doesn't affect the calculated font size until it sets the intended value at a certain viewport width. 

Mixing breakpoints and targets could, for example, look like this:

```html
<h1 class="font-1 font-3@md font-3@xl 5xl:font-14">Scale all the things</h1>
```

This set of utilities will keep the font static until the viewport reaches a medium size, where it jumps to the third step on the typescale. It keeps that size until the viewport hits its `xl` size, where it starts scalling smoothly towards `14` at `5xl`.

Importantly, you don't have to scale up as the viewport size increases: you can equally scale down, for example:

```html
<h1 class="font-1 font-2@sm sm:font-4 font-6@md font-3@xl">Whereas recognition of the inherent dignity</h1>
```

See `playground.html` for a more comprehensive list of examples and techniques.

## Contributing

This is an early release to showcase and explore the technique's potential and limitations—feedback and contributions are highly appreciated.