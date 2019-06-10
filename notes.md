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
* Alternatively, we could have have two `.eye` divs and given the right eye a second class of `.eye eye-right` and used `transform: translateX(120px);` to shift it to the right. That's a more modern approach 🤓. See [line 45](https://github.com/mostmojo/bear-ui/blob/master/style.css) in this example.
* Add the eyes in the same way as the ears. We can pretty much guess-timate the width and height percentages, then plug them into a formula. We can also use this formula to **dead center** absolute elements:
```
left = (100 - width) / 2
top = (100 - height) / 2
```
* We guess the width and height of the nose too, you may like koalas with larger noses! So, set as you like. Then, we have to give a higher `z-index` to the nose so it appears on top of the eyes. Use `border-radius: 50%` to get the rounded corners.
* Add inner-nose element and create a slight shade of lighter brown to make the nostrils. We also use `border-bottom` to get the curves. Use the more modern approach mentioned before to get the element `inner-nose--right` to the right using `transform: translateX(20px);`.
* For the `mouth` element, after setting width and height with `background color`, I realised it looked to block-y. So, used `border-bottom: 12px solid var(--grey-dark);` to create a straight line and add a `border-radius: 0 0 100% 100%;` skewing the corners to make a half moon shape 🌙.
* For the `hair-right` & `hair-left` elements we still use a square but `border-radius` wouldn't work as we want a triangle. We use `clip-path`'s `polygon` tool to cut out a triangle. Luckily, we find the shape we want on [clippy](https://bennettfeely.com/clippy/) and paste the polygon dimensions to make the clip-path magic happen.

* It's not as scary. We simply tell the browser that it has an X and Y axis. The first `50% 0` declares a point @ 50% of the containers x axis and 0 on the y axis. Then 0% x-axis and 100% y axis, and 100% x-axis and 100% y-axis makes the three points of a triangle, which the polygon cuts away 🙂. => 🔺

```
clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
```
