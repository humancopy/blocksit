BlocksIt.js – Dynamic Grid Layout jQuery Plugin
===============================================

BlocksIt.js is a jQuery plugin for creating dynamic grid layout. It manages to convert HTML elements into ‘blocks‘ and position them in well-arranged grid layout like Pinterest, one of the hottest website nowadays =). How? Well, simply specific the number of columns you wish to have and BlocksIt.js will do the rest for you. Also, you can even combine the ‘blocks‘ and make a huge block! So, let’s blocks it!

[Read here](http://www.inwebson.com/jquery/blocksit-js-dynamic-grid-layout-jquery-plugin/) the original article

How It Works
============

BlocksIt.js will re-position the selected elements using CSS absolute position property. It has the capability to calculate the top and left positions for an element based on certain criteria, like below:

1. Start the new block from left to right, and
2. Place the new block under shortest block.

How to use
==========
BlocksIt.js will re-position the selected elements using CSS absolute position property. It has the capability to calculate the top and left positions for an element based on certain criteria, like below:

1. First, include jQuery and .BlocksIt.js script files inside <head> tag like usual.

```javascript
<script type="text/javascript" src="jquery.min.js"></script>
<script type="text/javascript" src="blocksit.js"></script>
```

It should works well with jQuery 1.7.1 (haven’t tested for lower version).

2. Next, call the .BlocksIt() function on jQuery object. It supports for few settings, do refer to Configuration section below for deep details.
```javascript
$(document).ready(function() {
   $('#objectID').BlocksIt();
});
```

3. Done! =)

```
#Note: If the blocks contains of <img> element, be sure to specific the images' height before calling .BlocksIt() function, else you have to make sure the images are loaded.You could use $(window).load() to make sure everything have loaded into DOM, or use some plugin like [waitForImages](https://github.com/alexanderdickson/waitForImages) to check the images status.
```

Configuration
=============
.BlocksIt( [Options] )
Options: An array to configure blocks details.

Options
-------

Few options available:

| Name          | Type    | Default  | Description                                               |
| --------------|---------|----------|-----------------------------------------------------------|
| numOfCol      | Int     | 5        | The number of columns to be created.                      |
| offsetX       | Int     | 5        | Margin left and right for each block.                     |
| offsetY       | Int     | 5        | Margin top and bottom for each block.                     |
| blockElement  | String  | "div"    | Targeted child element, which will converted into blocks. |

![Grid Layout](https://raw.githubusercontent.com/humancopy/blocksit/master/src/grid-layout.png "Grid Layout")


Example of Configuration
========================

The HTML markup for blocks should look like below. data-size attribute specific the size of block (combined blocks).	

```html
<div id="container">
	<div class="grid class">...</div>
	<div class="grid class2" data-size="2">...</div>
	<div class="grid">...</div>
	<div class="grid class" data-size="3">...</div>
	<div class="grid">...</div>
</div>
```

```javascript
$(document).ready(function() {
   $('#container').BlocksIt({
      numOfCol: 5,
      offsetX: 8,
      offsetY: 8,
      blockElement: '.grid'
   });
});
```

License
=======
BlocksIt.js is licensed under the [GNU General Public License version 2](http://www.gnu.org/licenses/old-licenses/gpl-2.0.html) or later. You can do whatever you like to the source code. =)

