# Live HTML CSS and JavaScript Code Editor

Runs online or offline.

Hosted at: https://powerfulillusion.com/live-html-css-js-editor/

## Project Goal: Build an online live HTML/CSS/JavaScript code editor like Codepen that updated an webpage as you typed

This project was built upon my previous experiences reverse-engineering syntax highlighting, working with textarea's, and working with iframes.

## What it Ultimately Does

**The gist of it**: Gets the HTML, CSS, and JavaScript code on keyup events; displaying highlighted syntax and combining the HTML, CSS, and JavaScript for output to an iframe and running the JavaScript within the iframe.

## Details on Learning How to Create / Reverse Engineer the Different Parts

### The Full Web Application Initial Approach

I had read from several sources that some online HTML/CSS/JavaScript editors were based on a project called CodeMirror (https://codemirror.net) and this seemed like a great starting point and is arguably a quicker option for just grabbing functionality like displaying code in portions of your website with syntax highlighting. I read through a lot of the documentation, examined many examples from the CodeMirror repository, and eventually thought to myself "This has got to be easier and more fun to just reverse engineer so I can at least understand my product fully and be able to maintain it easily without having dependencies." (Not reverse engineering CodeMirror entirely, just creating the functionality I was looking for). 

I _**HATE**_ dependencies, but appreciate the work involved to make them, at least for HTML, CSS, and JavaScript. I completely love dependencies at those times when I need some complex operations performed and am on time constraints; although I'm always interested in actually writing the code to do anything just to learn and understand what I'm doing to the fullest extent possible. There are so many things in software I'm dependent on such as the operating system, web browsers, Internet, etc. I'm _**SO THANKFUL**_ for these inventions and wish I could discuss with every creator of them anything at all including their inventions.

#### Sidenote on the Freedom from Dependencies

Most things I remain dependent on but I enjoy working out how to emulate the functionality of any software. When it came to JavaScript in particular I had to be dependent on things due to them being implemented into products where I worked and having experience with them being a benefit when it came to submitting resumes. One of things that really inspired me to dedicate a large majority of my free time to learning and working with only JavaScript, besides it being implemented in browsers and the dependencies being hidden for it to run, was a website called "You Might Not Need jQuery" (https://youmightnotneedjquery.com). I had been using jQuery before working with it as a dependency professionally during my career because at some point in time it became apparent to me that doing a lot of things I wanted to do often had examples written in jQuery. I picked up jQuery because it seemed easy enough to link to in my HTML from a CDN or local file and then I could implement the examples I came across which often had shorter amounts of code and were voted up to the top on sites like StackExchange. I was already **VERY** familiar with CSS before ever really learning JavaScript, even to the point of creating simulated .onclick events using CSS attributes applied to HTML elements like radio buttons (e.g. radio-option::focus .class-i-want-location-of-element-changed-to { top: (#)px; left: (#)px; }). You Might Not Need jQuery encouraged me by showing me examples of many of the common functionalities of jQuery written with just a little more plain JavaScript sometimes in combination of CSS. I read through some of jQuery's source code one day and decided to reverse engineer implementation of the "$" since it seemed easy enough to do, then emulated jQuery's id and class targeting functionality before leaving it at that. 

### Syntax Highlighting

At several points in the past I've wanted to figure out on my own methods of syntax highlighting in a web-based text editor. While not done exactly like many other implementations, due to my reverse engineering it, the methods may be similar to existing implementations. I've never really searched out how to do it. I figured I could just take the text from a textarea or contenteditable HTML element and replace certain characters with HTML spans with classes added to them to color them and then output the HTML to an element's .innerHTML. When I first went about it I initially had two separate areas, one with a contenteditable HTML element and one used to display the syntax highlighted HTML. 

Both the contenteditable HTML element and textarea worked fine for just grabbing the element's inner text or HTML. I was heading in two directions initially with trying to maybe build out a web-based word processor where getting the HTML content from a contenteditable HTML element would be necessary but eventually dropped working on that for the time being to focus just on code syntax highlighting. 

During this project I realized I needed to drop the contenteditable HTML element entirely so I could get information on line numbers like you can using a textarea element's functionality.

