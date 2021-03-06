# Sliding Puzzle
Sliding Puzzle is a funny jQuery plugin that lets you cover a grid in your layout with a sliding puzzle that uncovers your grid elements randomly or lets the user slide the tiles manually.

1. [Features](#features)
2. [Usage](#usage)
3. [Demo](#demo)
4. [Requirements](#requirements)

# Features
- Defrag Intro: Puzzle cover breaks into tiles the first time the user sees it, with a "flipping card" animation
- Autoplay: Tiles move randomly uncovering grid elements underneath. A tile moved on a direction will never move back on the next step, but rather choose a different direction between those available.
- Pause on Blur: Game will pause when the window will lose focus of the puzzle is scrolled out of view.
- Smooth Drag: Users can drag tiles smoothly to slide between grid elements.
- Responsive: Tiles will be resized when the page width changes, however the puzzle will pause and tiles will be reset to default position
- Touch support: Should be working nicely with all touch devices, however multitouch may cause issues


# Usage
Load the plugin on your page:

```
<script src="./sliding-puzzle.min.js"></script>
```


Add configuration:

```
$( document ).ready(function() {
	var activeProperties = {
		boxShadow:	'box-shadow: inset -1px 2px 5px 0px rgba(50, 50, 50, 0.35)',
	};

	var inactiveProperties = {
		boxShadow:	'none',
	};
	
	var options = {
		wrapperClass:		'className',				// class name of your grid container
		elementClass:		'className',				// class name of your grid elements
		playButton:			'className',				// class name of play button
		pauseButton:		'className',				// class name of pause button
		resetButton:		'className',				// class name of reset button
		activeProperties:	activeProperties,			// CSS properties to apply when button is active
		inactiveProperties:	inactiveProperties,			// CSS properties to apply when button is inactive
		rows:				3	,						// number of rows													 default: 3		 min: 2
		columns:			3	,						// number of columns												 default: 3		 min: 2
		emptyTileIndex:		2	,						// index of the empty tile, 0 = first tile, 1 = second tile, etc	 default: 0		 min: 0		max: rows*columns
		playInterval:		2000,						// interval between tiles move, must be higher than animDuration	 default: 1000	 min: 1000
		animDuration:		1000,						// duration of move animation, must be lower than playInterval		 default: 500	 min: 500
		coverBackgroundURL:	'url/to/image.png',			// url to the background image for the cover
		tilesBackgroundURL:	'url/to/image.png',			// url to the background image for the tiles
		loaderURL:			'url/to/image.gif',			// url to the loader image
		flipOnVisible:		true,						// flip the tiles only when the game container is visible			 default: false
		pauseOnBlur:		true,						// pause auto-play if the page loses focus or the user scrolls out	 default: true
	}
					
	var puzzle = new SlidingPuzzle(options);
});
```


# Demo

Basic example with 3x3 grid
http://www.rigo7.com/projects/sliding-puzzle?source=git


# Requirements
- jQuery
- CSS3 'transform' property (Chrome 36.0, IE 10.0, Mozilla 16.0, Safari 4.0, Opera 23.0)
