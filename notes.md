### Notes

* Set the root colors first. Vars come in handy when your future self decides to change the color of the whole project.
* Start with applying a background to the body.
* Style the invisible box. The invisible box will be centered horizontally(if you're following along to visually see how the position of the box changes, you can set a solid border): `.box { border: solid 4px red; }`. When the position is set to `relative`, using `display: block;` and `margin:auto;` will automatically center the box horizontally.
* Alternatively, we could set the .box element to `position: absolute` and all the other divs too. This would be positioned absolute to the relative body or window object which is `top: 0; left: 0;`, so if that route is chosen, our code would look like this:

```
.box {
	position: absolute;
	width: 200px;
	height: 100px;
	margin: auto;
	top: 0;
	right: 0;
	bottom: 0;
	left: 0;
}
```

* We'd have to position all the corners to zero to make it centered.

* Now that our box is set, all of our other divs will be nested within the box. This is important as we will assign an absolute positions (top, right, left, or bottom) by *percentage*, that will position a div that percentage from the box and **not** the body. The same concept will also apply with our height and width percentages.
* The % for top and left mean that the div will be 15% from the top of the invisible box and 25% from the left of the box. The width of the div is 50% and the height 67% - of the box div. Then we give it a background color.
* The `head-copy` div is solely for the purpose of allowing the ears to appear behind the head. This is controlled by `z-index`. We give `head-copy` a `z-index: 2` so when it's time for the ears to be placed behind the head, we'll give them `z-index: 1`.
* We create the `ear-left` and `ear-right` divs and position them relative to the `head` element. We also nest the `inner-ear` which will be a darker shade of grey in each ear. Remember: set width & height to make a square element, then `border-radius: 50%` to create a circle.