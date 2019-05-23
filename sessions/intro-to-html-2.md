# HTML II: Documentation and Debugging Tools

<!-- To Do List/Items: -->

<!-- 
- Chart paper with HTML, CSS, JS drawings
- Write password for internet on the board
- Write URL for DSST repo on board -->

## Learning Goals

- Utilize technical documentation to help solve computer programming problems
- Utilize Chrome DevTools to debug and make changes to websites

## Vocab

- `Dev Tools` web development tools built into the Chrome Browser
- `Technical Documentation` written documents and materials dealing with software product development
- `Form` a document section that has interactive controls for submitting info

# Overview
Now that you have a handle on the basics of structuring content for an HTML file:

* Let's discuss building more robust HTML __forms__
* Let's start using our __devtools__

# Docs

HTML Guide and form structure
* [MDN HTML Forms Guide](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms)
* [MDN How to Structure an HTML Form](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms/How_to_structure_an_HTML_form)

Dev Tools
* [Chrome Dev Tools Docs](https://developers.google.com/web/tools/chrome-devtools/)
* [The Basic of Chrome Dev Tools](https://www.udemy.com/devtools-2017-the-basics-of-chrome-developer-tools/)

***

# Forms

<!-- Ask for examples of forms that they've used on websites/interactions -->

Forms are an important part of a website. They allow users to send data to the web site. Most of the time that data is sent to the web server, but the web page can also intercept it to use it on its own. Forms are comprised of the following base elements:

* `form`
* `label`
* `input`
* `submit`

<p data-height="300" data-theme-id="26495" data-slug-hash="JbyeZM" data-default-tab="html,result" data-user="turing" data-embed-version="2" data-pen-title="Super Basic HTML Form" data-editable="true" class="codepen">See the Pen <a href="http://codepen.io/team/turing/pen/JbyeZM/">Super Basic HTML Form</a> by Turing School of Software and Design (<a href="http://codepen.io/turing">@turing</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<!-- <script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script> -->


## Your Challenge

Copy the form code below into your own Pen, and then refactor as follows:

* Validate for email type
* Include placeholders for name, email, and message
* Add a drop down for favorite color with at least three options
* Use an input for submit instead of a button

<p data-height="458" data-theme-id="26495" data-slug-hash="Lbjgwy" data-default-tab="html,result" data-user="turing" data-embed-version="2" data-pen-title="Basic HTML Form" data-editable="true" class="codepen">See the Pen <a href="http://codepen.io/team/turing/pen/Lbjgwy/">Basic HTML Form</a> by Turing School of Software and Design (<a href="http://codepen.io/turing">@turing</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<!-- <script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script> -->

***

# Chrome Dev Tools

<!-- Tell a story about using dev tools -->

Debugging your front-end code can be an intimidating part of the development process, but it's also one of the most powerful skills you can acquire Developers of all levels spend a significant amount of time troubleshooting code, but the more comfortable you are with debugging tools, the easier it will be to isolate, identify and fix broken code.

The front-end languages (HTML, CSS and JavaScript) are run entirely in the browser, so the technique for troubleshooting broken code can happen in many places. Luckily, modern browsers are aware of this and give us a collection of advanced tools to help us debug.  

Take 5 minutes to read through [this section](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/) of the chrome devtools docs.

### Developer Tools
One of the first tools you should familiarize yourself with when doing front-end development are the built-in browser [DevTools](https://developer.chrome.com/devtools). To open developer tools in Chrome:
  - Mac: `Cmd` + `Opt` + `i`
  - (or) Right click on the browser window and select `inspect`
  - (or) Select `View` in the navbar, then `Developer`, then `Developer Tools`

Personally I find that pinning the dev tools to the upper right is the most convenient. (You can also expand them into their own window.)

![devtools window][devtools-window]

### The Panels
Once you have your DevTools window open, you'll notice a toolbar across the top with several different tabs. Clicking on these tabs will bring you to different debugging panels, each built to help troubleshoot specific areas of your front-end code.

As mentioned earlier, there are a lot of places on the front-end where code can go wrong. This means the first and most important step in solving a bug is **isolating the problem**. DevTools has already done some of this step for us by categorizing the most commmon areas where developers run into problems, and providing us with specific debugging panels for each.

![devtools toolbar][devtools-toolbar]

For now, we're only going to focus on the first panel: Elements.

[devtools-window]: /assets/devtools-window.gif
[devtools-toolbar]: /assets/devtools-toolbar.png

---------------------------------------

### The Elements Panel: Debugging HTML, CSS & DOM Events

##### HELPFUL FOR:
* debugging layout and styling issues
* checking DOM Events

The elements panel lets you view the entire HTML source of the current page you are viewing. From here, you can edit, add or remove content and elements directly on the page. Though your changes won't be saved (any changes made here will be lost upon refreshing the page), sometimes it's helpful to make tweaks directly in this panel so you can see what effect the changes will have on your application before you implement them.

![Elements Panel][elements-panel]

### Selecting Elements to work with
You'll notice hovering over an HTML element in the devtools panel will also highlight that element on the page. This makes it easier to find and select the content you'd like to work with.

You can also select elements directly on the page by clicking the ![Square Arrow](http://i.imgur.com/ODylyUu.png) icon in the toolbar, then hovering over the element on the page. This will automatically bring you to the corresponding code for that element in the devtools panel.

If you're having trouble finding the element you'd like to work with, you can search through the entire HTML with `Cmd + F`. You'll notice a searchbar appear at the bottom of the panel where you can enter any string to find a match. This is useful if you'd like to search for an element by a known ID or class.

![Find in HTML][find-in-html]

## Your Challenge
Directly from the elements panel, we can edit the HTML and see the changes reflected immediately. (Again, these changes won't be saved to your codebase, but sometimes it helps to see the tweaks as you make them before committing to them.)

Let's work with the following edits on [girldevelopit.com](https://www.girldevelopit.com/):

* Change the headline to read: "Just Do It. Write Code"
* Hide the element that contains the map
* Delete the press logos section
* Place the top nav of "supporters" in its hover state
* Change the "flourish" logo in the headline to one of puppies

[elements-panel]: /assets/elements-panel.png
[find-in-html]: /assets/find-in-html.gif

### Journal

- Why is programming documentation important?
- What are Chrome Dev Tools? Why do we use them?