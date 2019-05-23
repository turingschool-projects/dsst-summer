# CSS: Styling, Positioning

<!-- To Do List/Items: -->

<!-- 
- Papers and markers for demonstrating positioning in CSS. 1 paper per student
- Chart paper with a border to represent the `section` border in the positioning exercise. 1 chart paper per 3 students
- Write password for internet on the board
- Write URL for DSST repo on board -->

## Learning Goals

- Understand the basics of CSS and apply these concepts to add styling to HTML structures
- Demonstrate how CSS positioning allows us to decide where elements are placed
- Build a small static site and style our markup using a separate style sheet of basic CSS 

## Vocab

- `CSS` Cascading Style Sheets
- `CSS property` The name of a display property of an HTML element (e.g., color, border)
- `id` / `class` Ways to identify/target HTML elements

# Overview

The front-end of the web is based on three major technologies: HTML, CSS, and JavaScript. Today we are going to focus on CSS:

* __CSS aka "PRESENTATION"__:  Cascading Style Sheets (CSS) sets the look and style of a web page. CSS provides style to the structure provided by HTML.

<!-- Possible analogies to use:
HTML = HOUSE
CSS = PAINT/CARPET
JS = TURNING ON LIGHTS/FUNCTIONALITY -->

## What is CSS?

It’s a “style sheet language” that lets you style the HTML elements on your page. CSS works _with_ HTML, but isn't HTML. CSS controls the positioning, sizing, colors, and specific fonts on your page. 

There is a `class` and `id` attribute available to use on __every__ html element. In addition to the plain old tag names themselves, these attributes allow you to create "targets" for both your css and javascript. They are hooks so that you can manipulate the look and behavior of your HTML elements.

Let's take a look at [CSS Zen Garden](http://www.csszengarden.com/), a website that showcases what can be accomplished with CSS.

## Anatomy of a Basic CSS Rule

# ![CSS Rule](/assets/css-rule.png)

* Can target via tag name
* Can target via class name
* Can target via id name
* Can target via a combination of above

<p data-height="300" data-theme-id="26495" data-slug-hash="KNvbQX" data-default-tab="html,result" data-user="turing" data-embed-version="2" data-pen-title="CSS Rules" data-editable="true" class="codepen">See the Pen <a href="http://codepen.io/team/turing/pen/KNvbQX/">CSS Rules</a> by Turing School of Software and Design (<a href="http://codepen.io/turing">@turing</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<!-- <script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script> -->

## All the Elements are Boxes
Each element is a rectangular box. CSS leverages "the box model" to control layout and design. An HTML element is comprised of its content and the margins, borders, padding surrounding it. Boxes are "stacked" in the order they appear in your HTML. You can stack them horizontally, vertically, and in the z-plane.

# ![Box Model](/assets/box-model.jpg)

***

# The Docs

* [MDN CSS Box Model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model)
* [MDN CSS Overview](https://developer.mozilla.org/en-US/docs/Web/CSS)
* [Visual Guide to CSS](http://cssreference.io/)

***

## Don't Forget Your Dev Tools!

#### Editing CSS
To the right of the HTML pane, there's a small sidebar that gives us styling information for the currently selected element. Similar to the HTML pane, we can add or remove styles and adjust CSS property values from this pane. You can click on any style property associated with the selected element and change its value. You can also use the blue checkbox to toggle the style on or off.

![Editing CSS](/assets/editing-css.png)


### Your Challenge
Directly from the css panel, we can edit the css and see the changes reflected immediately.

Let's work with the following edits on [girldevelopit.com](https://www.girldevelopit.com/):

* Change the background color of the header to chartreuse
* Change the headline text color to magenta.
* Change the "flourish" logo in the headline to have a height of 20px
* Hide the element that contains the map using css

# Practice
Let's setup a small static page to experiment with our HTML and CSS.

* Open up a new pen on CodePen and title it `CSS Playground`
* Using the template below, set up your HTML file

```html
<head>  
  <title>CSS Playground</title>
</head>  
<body>  
  <h1>Static Site Experiments in Here!</h1>
</body>  
```

## Let's draw some boxes and play with some basic CSS properties

* Box Model things: `width`, `height`, `border`, `padding`, `margin`
* Aesthetic things: `color`, `font-family`, `background-color`

## Document Flow is Important

The document flow is the model by which elements are rendered by default in the CSS specifications. In this model, elements are rendered according by their default display rule. In other words, block-level elements are displayed on a new line and inline elements on the same line. Everything is stacked in an ordered way from top to bottom. The document flow can be modified by CSS through its positioning properties.

- CSS divides HTML elements into two types: inline and block
- After block elements, browsers render a new line
- Inline elements: `img`, `a`, `br`, `em`, `strong`
- Block elements: `p`, `h1`, `ul`, `li`, almost everything else

### Display Property

- The default value for all elements is inline. Most "User Agent stylesheets" (the default styles the browser applies to all sites) reset many elements to "block".
- **Inline:** `<span>`, `<em>` Text wraps around me! I accept margin and padding, but only push things horizontally, not vertically. I am going to politely ignore your height and width instructions.
- **Inline-Block:** An element set to `inline-block` is very similar to inline in that it will set inline with the natural flow of text (on the "baseline"). The difference is that you are able to set a `width` and `height` which will be respected.
- **Block:**  A number of elements are set to block by UA stylesheets, usually container elements. `<div>`, `<ul>`, `<section>`, and a bunch more. Also, text blocks like: `<p>`, `<h1>`. I do not sit inline! I will take up as much horizontal space as possible!

```css
div {
  display: 'inline';        /* Default of all elements, unless UA stylesheet overrides */
  display: 'inline-block';  /* Characteristics of block, but sits in a line */
  display: 'block';         /* UA stylesheet makes things like <div> and <section> block */
  display: 'none';          /* Hide */
}
```

<!-- Talk about using inline block when changing inline to block -->

### Position Property

- We can manipulate this [code pen](https://codepen.io/damwhit/pen/POxbPV) to play around with the following values for our position property.
- `relative`: A relatively positioned element preserves its space. The adjacent elements aren’t repositioned to occupy the reserved space for this element. However, the offsets of this element don’t occupy space. They’re completely ignored from the other elements, and hence that may causes elements to overlap each other.
- `absolute`: An absolutely positioned element is completely removed from the normal flow. The adjacent sibling elements occupy its space.
- `fixed`: A fixed positioned element (subcategory of the absolute positioning) is positioned relative to the viewport. It will stick in place despite any scrolling or resizing of the viewport
- You specify the position of your element via offset properties: `auto` (default), `top`, `bottom`, `right`, `left`
- An element whose position property is set to absolute or fixed is called an absolutely positioned element.
- A positioned element can take advantage of the `z-index` property to specify its stack order. The stack order is the order in which elements in the same space lay on top of one another. For example, an element with a `z-index` of `2` will appear above an element with a `z-index` of `1` if they happen to overlap. Without any z-index value, elements stack in the order they appear in the DOM (the lowest one down at the same hierarchy level appears on top). Elements with non-static positioning will always appear on top of elements with default static positioning. Also note that nesting plays a big role. If an element B sits on top of element A, a child element of element A can never be higher than element B.


<!-- 
  Start by using the codepen to demonstrate differences in positioning. Transition into using papers with colored squares to demonstrate positioning. 

  After the demonstration, have each student color a square on a single sheet of paper. Place students in groups of 3 (each student should have a different color for their square) to work through a positioning exercise -->

#### Your Turn

Gather into a group of 3. Make sure each person in the group has a different color. Use this `HTML` and line up accordingly:

```html
<section>
  <div class="human1"></div>
  <div class="human2"></div>
  <div class="human3"></div>
</section>
```

Once you are ready to go, try the following:

- `human1` should set their positioning to `absolute`
- Reset
- `human2` should set their positioning to `absolute` and `right: 0`
- Reset
- `human3` should set their positioning to `absolute` and `top: 0`
- `section` is now set to positioning `relative`. What happens when `human1` sets the property of `right:0`?

### Floats
"Floating" an element takes it out of the normal flow, and places it as far to the left or right of its containing element as possible. Any other elements, such as paragraphs or lists, will wrap around the floated element as seen [here](https://codepen.io/damwhit/pen/RMRKaW). (It was originally intended only for magazine style text wrapping.)

- Always specify a width when floating an element, otherwise the element is likely to take up the whole page and not appear floated.
- You can specify a) whether an element is floated or not, and b) which side it ﬂoats on.
- `none`: the element does not float. This is the initial value.
- `left`: floats the element to the left of its container.
- `right`: floats the element to the right of its container.
- `inherit`: the element inherits the float direction of its parent.
- `clear`: Float's sister property. An element that has the clear property set on it will not move up adjacent to the float like the float desires, but will move itself down past the float.
- We can play around with this [code pen](https://codepen.io/damwhit/pen/KZjBPK) to see how float and clear work with one another.

<!-- Don't go down the rabbit hole of figuring out how to explain clearfix hack -->

```css
.clearfix:after {
    content: ' ';
    display: table;
    clear: both;
}
```

***

# CSS Specificity
__Specificity__ is how the browser decides which CSS values are the most relevant to an element and whether or not they should be used.
__Specificity__ is a weight that is applied to a given CSS declaration and is determined by the number of each selector type in the matching selector.
Basically, it’s a mechanism within the CSS cascade, which helps browsers in conflicts resolution. Suppose, you have two (or more) conflicting CSS rules that are being applied to the same element, then there are going to be some basic rules which a browser will follow to determine which one is most specific and that particular CSS declaration will win.

### What does specificity look like?


<!-- Write example on the whiteboard to go with CSS -->

```css

// This makes all the <li> tags magenta
li {
  color: magenta;
}

// This indicates that all <p> tags within an <li> tag should have text color of green
li p {
  color: green;
}

```

### How do you calculate specificity?

<!--
  write a simple tag on the whiteboad with a simple class
  write the corresponding to css
 -->

To find the actual specificity of a group of nested selectors takes some calculation. Basically, every inline style has a specificity of 1000, every ID selector has a value of 100, every class selector has a value of 10 and every element has a value of 1. Finally, we add them up to get the specificity weight

Examples:

* `a` has a specificity of 1 (1 element selector)
* `div p` has a specificity of 2 (2 element selectors, 1+1)
* `.active` has a specificity of 10 (1 class selector)

[Specificity Calculator](https://specificity.keegan.st/) The highest number wins for most specific and will correspondingly take precedent in application of style.

Key Points:

* In case of conflicting styles declaration, the declaration with higher specificity will win regardless of order.
* The universal selector (*) has no specificity value.