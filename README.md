# Overview
A simple SCSS grid solution, built on top of flexbox.

# Installation
Barebones is available on npm and bower.

`$ npm install barebones.scss`

`$ bower install barebones.scss`

Alternatively, you can just clone this repo. I'm not particularly opinionated on how you do this. Want me to add a process? Feel free to make an issue!

# Usage

Import the [barebones.scss](https://github.com/hmphry/barebones/blob/master/source/_base.scss) base file. From there, you can either use as is, or customize the settings to create your own grid.

Base barebones is:
* On screen sizes ranging from 0px to 760px:
  * 4 columns
  * prefix = m
  * 10px padding and gutters
* On screen sizes ranging from 761px to 1120px:
  * 12 columns
  * prefix = t
  * 20px padding and gutters
* On screen sizes ranging from 1121px and up:
  * 12 columns
  * prefix = d
  * 20px gutters
  * 60px padding

# Customization

Customizing barebones is pretty effortless. Simply define a map of your settings called `$barebones`. `$barebones` has several optional... options... that can be defined.

- `namespace`: Optional. String. Defines the name of grids, default is "grid".
- `box-sizing`: Optional. String. Accepts "content" or "border";
- `layouts`: Optional. Map. Accepts map of defined grids. Important to not that while layouts is optional, most of the values within each grid are not.

`layouts` is where a bulk of the magic will happen. Here, you can define grids, as many as you wish! Each grid allows several customization options.
- `name`: Optional. String. Mostly for readability. Does not get injested by barebones.
- `prefix`: String. How you want each class for the grid to begin.
- `start`: Pixel Value. Minimum browser width for grid availability. To start at 0, use `false`.
- `end`: Pixel Value. Maximum browser width for grid availability. To be endless, use `false`.
- `columns`: Integer. Number of columns within the grid.
- `gutter`: Integer. Pixel value of padding between each column.
- `padding`: Integer. Pixel value of padding on the outside of the grid.

Want a grid with no padding and no gutters? gg ez:
````
$barebones:
	namespace: "grid",
	box-sizing: "content",
	layouts: ((
		name: mobile,
		prefix: m,
		start: false,
		end: 760px,
		columns: 4,
		gutter: 0,
		padding: 0
	), (
		name: tablet,
		prefix: t,
		start: 761px,
		end: 1120px,
		columns: 12,
		gutter: 0,
		padding: 0
	), (
		name: laptop,
		prefix: d,
		start: 1121px,
		end: false,
		columns: 12,
		gutter: 0,
		padding: 0
	));
````

Want to micromanage one grid? No sweat!
````
$barebones:
	namespace: "grid",
	box-sizing: "content",
	layouts: ((
		name: mobile,
		prefix: b,
		start: false,
		end: 400,
		columns: 12,
		gutter: 0,
		padding: 10
	),(
		name: larger mobile,
		prefix: b,
		start: 400,
		end: 800,
		columns: 12,
		gutter: 10,
		padding: 20
	), (
		name: tablet,
		prefix: b,
		start: 801px,
		end: 1000px,
		columns: 12,
		gutter: 10,
		padding: 20
	), (
		name: larger tablet,
		prefix: b,
		start: 1001px,
		end: 1200px,
		columns: 12,
		gutter: 20,
		padding: 20
	), (
		name: laptop,
		prefix: b,
		start: 1201px,
		end: false,
		columns: 12,
		gutter: 20,
		padding: 60
	));
````

Want to... I don't know... live on the edge and make like 10 different grids for all sorts of different things?! Fine, whatever. I'm not your god, your father, or your boss. You do as you wish!

````
I'm not going to mock this up because I *morally* object to it, but I assure you that it is possible.
````

Feel free to drop a line in the issues or reach out to me on [twitter](https://twitter.com/heyhmphry) should you ever need anything. <3
