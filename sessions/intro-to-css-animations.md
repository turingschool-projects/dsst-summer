# CSS: Animations

<!-- To Do list/Items: -->

<!-- - Have examples ready to show (Overview section) -->

## Learning Goals

- Understand and implement transitions, transformations, and animations in CSS
- Utilize programming documentation to complete CSS animation coding challenges

## Vocab
- `CSS Transition` defines the transition between two states of an element
- `CSS Transformations` allows for rotation, scaling, or skewing of an element
- `CSS Animations` makes animating transitions from one CSS style to another

# Overview 

This morning, we are going to continue to focus on CSS - specifically, animations. Turns out, CSS has some "behaviour tricks" up its sleeve. Through CSS transitions, transformations, and animations you can create quite a bit of movement on your page sans any real JavaScript. Check out some of these stunning examples:

* [Type Terms](https://www.supremo.tv/typeterms/)
* [Code Pen: Page Flip](http://codepen.io/fbrz/pen/whxbF?editors=1100#0)
* [Movie Posters](http://demo.marcofolio.net/3d_animation_css3/)
* [Coke Can](http://www.romancortes.com/ficheros/css-coke.html)
* [Album Covers](http://www.bluedashed.com/covers/)...okay, so there is some js happening in this one, but the covers were recreated using pure CSS.

### Definitions:

* CSS Transitions: CSS transitions allow property changes in CSS values to occur smoothly over a specified duration of time.
* CSS Transformations: By modifying the coordinate space, CSS transforms change the shape and position of the affected content without disrupting the normal document flow.
* CSS Animations: For more involved movement, we can use CSS animations rather than transitions and transformations. What's the difference? A transition is typically a state change that goes from A to B (like a :hover state), while an animation may have many stages from A to B to C to D.

# Docs

* [MDN CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)  
* [Animatable Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)
* [CSS Tricks Transform](https://css-tricks.com/almanac/properties/t/transform/)
* [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* [CSS Tricks Animation](https://css-tricks.com/almanac/properties/a/animation/)

# Practice

Let's create some pens!
But first - rearrange yourselves so that you can pair up with a new partner! Someone you have not yet paired with in a class exercise or a project.

### Code Pen #1

Setup a div with the following styles:

```css
  background-color: yellow;
  border-radius: 30px;
  height: 300px;
  width: 300px;
  margin: 0 auto;
```

1. Create a pseudo class of `hover`. On hover, the div should transition background color on a 2s delay. (Hint: `transition-property` & `transition-duration` are things)
2. What happens with the transition when you move your cursor off the div?
3. Move the transition properties out of the hover state and onto the base div. What is different now when you move your cursor off the block?
4. You can chain properties together that you want to transition. Change the background-color and border-radius at the same time, but set them to different duration speeds. The border of the box should transition from 30px to 0.
5. Assuming you have successfully completed steps 1-4, now delete the `transition-property` line of code. Does your animation still work? Why?

### Code Pen #2

Setup:

```html
<div class="container">
  <div class="box"></div>
</div>
```

```css
.container {
  border: 1px solid grey;
  height: 400px;
  width: 90%;
  margin: 0 auto;
  padding: 15px;
}

.box {
  background-color: yellow;
  border-radius: 30px;
  height: 300px;
  width: 25%;
}
```
1. Create a hover state for the CONTAINER whereby the background color of the BOX changes to green.
2. Make the box move on hover by adding `margin-left: 75%`.
3. It's a stark transition. Smooth it out with a 1s transition that works when the user moves their cursor onto the container, and also works when they move their cursor off of the container.
4. Experiment with the following three values with the
   `transition-timing-function` on the container:
   * `transition-timing-function: ease;`
   * `transition-timing-function: steps(4, end);`
   * `transition-timing-function: cubic-bezier(1, -1, 1, .5);`
5. Discuss your observations from #4 and research the documentation to prove and clarify your observations.

### Code Pen #3
Setup:

```html
<div class="container">
  <div class="box"></div>
</div>
```

```css
.container {
  border: 1px solid grey;
  height: 400px;
  width: 90%;
  margin: 0 auto;
  padding: 15px;
}

.box {
  background-color: yellow;
  border-top: 5px solid red;
  height: 95px;
  width: 100px;
  -webkit-transform: rotate(45deg);
}
```

1. Rotate the box counter-clockwise 45 degrees
2. What happens when you pass rotate an argument of `.5turn` or `.75turn` or `2turn`
3. What are `scale` and `skew` transformations do? Use your documentation to implement those when you hover over the box.

### Code Pen #4

Setup:

```html
<div></div>
```

```css
div {
  background: yellow;
  height: 200px;
  width: 200px;
  margin: 100px auto 0;
}

@keyframes testAnimation {
  0% {
    transform: rotate(360deg);
    border-radius: 50% 0 50% 0;
  }
  100% {
    background-color: aqua;
    border-radius: 0 50% 0 50%;
  }
}
```

1. Discuss with your partner what the keyframe Animation that we've named `testAnimation` will do
2. Now connect the defined keyframes (testAnimation) to the div by adding the following declaration the div:
```css
  animation-name: testAnimation;

```
3. Create a 3s duration for the animation
4. Create a zero animation delay
5. Create an infinite iteration count
6. Create a linear timing function 
7. Set the animation direction to alternate
8. Extra challenge: Try to combine these declarations using the shorthand `animation` property

### Code Pen #5 :facepunch: :dizzy_face:
Go crazy. Experiment with all you've just learned and make a 4-stage animation(s). Hint: code pen #4 was a 2-stage animation. 

## Closing

- What is one new thing that you learned about CSS animations that wasn't covered in the lesson?
- What are two questions that you have about what we covered?
- Could you have too many animations/transitions/transformations on a website or application? Defend your answer.
