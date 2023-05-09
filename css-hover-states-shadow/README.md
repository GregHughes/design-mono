# Animated hover states w/ box shadow

This is a pretty standard pure-CSS design for a hover state that scales the element and adds a box-shadow. It looks good just about everywhere.

## config

Just the important styles for transform, box-shadow, and transition.

```css
.hover-item {
transition: 0.2s ease-in-out;
}

.hover-item:hover {
/_ More info on transform distortion fixes: https://stackoverflow.com/questions/14677490/blurry-text-after-using-css-transform-scale-in-chrome _/
/_ for scale use 1.048 instead of 1.05 for a better approximation to a whole-pixel font size, reducing the sub-pixel blurring _/
/_ use translateZ(0) to add hardware acceleration to the animation _/
transform: scale(1.048) translateZ(0);

/_ better rendering _/
-webkit-font-smoothing: subpixel-antialiased;
/_ simplifies the animation to just the front of the object, whereas the default state is the front and the back _/
backface-visibility: hidden;

box-shadow: 0 2.8px 2.2px rgba(0, 0, 0, 0.034),
0 6.7px 5.3px rgba(0, 0, 0, 0.048), 0 12.5px 10px rgba(0, 0, 0, 0.06),
0 22.3px 17.9px rgba(0, 0, 0, 0.072),
0 41.8px 33.4px rgba(0, 0, 0, 0.086), 0 100px 80px rgba(0, 0, 0, 0.12);
}
```
