### Notes

* I like to set the root colors first. Vars come in handy when your future self decides to change the color of the whole project.
* Start with applying a background to the body.
* Style the invisible box. The invisible box will be centered horizontally(if you're following along to visually see how the position of the box changes, you can set a solid border): `.box { border: solid 4px red; }`. When the position is set to `relative`, using `display: block;` and `margin:auto;` will automatically center the box horizontally.

Now that our box is set, all of our other divs will be nested within the box. This is important as we will assign an absolute positions (top, right, left, or bottom) by *percentage*, that will position a div that percentage from the box and **not** the body. The same concept will also apply with our height and width percentages.