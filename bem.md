BEM
===

## Block

A functionally independent page component that can be reused. In HTML, blocks are represented by the class attribute.

The block name describes its purpose ("What is it?" — menu or button), not its state ("What does it look like?" — red or big).

### Nesting

- Blocks can be nested in each other. 
- You can have any number of nesting levels.

Example:

	<div class="block">
	    <div class="block__elem1">
	        <div class="block__elem2">
	            <div class="block__elem3"></div>
	        </div>
	    </div>
	</div>


	.block {}
	.block__elem1 {}
	.block__elem2 {}
	.block__elem3 {}


This HTML structure allows the modification of the HTML without modifying the CSS. For instance, the following HTML has the same CSS as before.

	<div class="block">
	    <div class="block__elem1">
	        <div class="block__elem2"></div>
	    </div>
	    <div class="block__elem3"></div>
	</div>

## Good links

- https://en.bem.info/methodology/quick-start/