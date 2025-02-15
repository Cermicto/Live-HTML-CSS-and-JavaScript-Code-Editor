# Live HTML, CSS, and JavaScript Code Editor

Runs online or offline.

Hosted at: https://powerfulillusion.com/live-html-css-js-editor/

## Project Goal: Build an online live HTML/CSS/JavaScript code editor like Codepen that updated an webpage as you typed

This project was built upon my previous experiences reverse-engineering syntax highlighting, working with textarea's, and working with iframes.

## What it Ultimately Does

**The gist of it**: Gets the HTML, CSS, and JavaScript code on keyup events; displaying highlighted syntax and combining the HTML, CSS, and JavaScript for output to an iframe and running the JavaScript within the iframe.

## Details on Learning How to Create / Reverse Engineer the Different Parts

### The Full Web Application Initial Approach

I had read from several sources that some online HTML/CSS/JavaScript editors were based on a project called CodeMirror (https://codemirror.net) and this seemed like a great starting point and is arguably a quicker option for just grabbing functionality like displaying code in portions of your website with syntax highlighting. I read through a lot of the documentation, examined many examples from the CodeMirror repository, and eventually thought to myself "This has got to be easier and more fun to just reverse engineer so I can at least understand my product fully and be able to maintain it easily without having dependencies." (Not reverse engineering CodeMirror entirely, just creating the functionality I was looking for). 

I completely love dependencies at those times when I need some complex operations performed and am on time constraints; although I'm always interested in actually writing the code to do anything just to learn and understand what I'm doing to the fullest extent possible. There are so many things in software I'm dependent on such as the operating system, web browsers, Internet, etc. I'm _**SO THANKFUL**_ for these inventions and wish I could discuss with every creator of them anything at all including their inventions.

(See **Sidenote on the Freedom from Dependencies** at the bottom of this README.md and also **Why Web Development Frameworks Were Born and why so Few Exist in My Opinion** for some insights gleaned during my developer experience)

### Syntax Highlighting

At several points in the past I've wanted to figure out on my own methods of syntax highlighting in a web-based text editor. While not done exactly like many other implementations, due to my reverse engineering it, the methods may be similar to existing implementations. I've never really searched out how to do it. I figured I could just take the text from a textarea or contenteditable HTML element and replace certain characters with HTML spans with classes added to them to color them and then output the HTML to an element's .innerHTML. When I first went about it I initially had two separate areas, one with a contenteditable HTML element and one used to display the syntax highlighted HTML. 

Both the contenteditable HTML element and textarea worked fine for just grabbing the element's inner text or HTML. I was heading in two directions initially with trying to maybe build out a web-based word processor where getting the HTML content from a contenteditable HTML element would be necessary but eventually dropped working on that for the time being to focus just on code syntax highlighting. 

During this project I realized I needed to drop the contenteditable HTML element entirely so I could get information on line numbers a textarea element's functionality.

Basically, there are textarea elements for each HTML, CSS, and JavaScript editor area that have transparent text and backgrounds while keeping the cursor visible. On keyup of one of the textarea elements the value of the text area is processed into HTML with spans around specific characters, or beginnings or endings of spans when it comes to text like the beginning or ending of tags or quotes, then the HTML with the spans having class attributes to style them are placed in an HTML div element directly underneath the transparent text area with the same font-size, line-height, etc. so it matches up with the textarea's location of the text and cursor.

### Line Numbering and Current Line Highlighting

...to be continued...

### Reverse Engineering and Creating Emulators is the most Fun and Valuable Learning Experience in my Opinion

I've learned a lot reverse engineering, or sometimes emulating, many levels of software application and hardware functionality as web browser or server-side implementations using JavaScript and Node.js. 

- I've programmed a virtual CPU with virtual registers and created an assembly language interpreted by parsing it with JavaScript to run on it.
- I've coded a database implementation that used Node.js API endpoints and local file storage that accepted standardized REST API http/https calls or even standardized and encrypted SQL SELECT statements sent from the browser using AJAX XMLHttpRequest (although I'm still familiar with async/await promises and fetch, I wanted more management and understanding of handling requests myself). I learned something useful in my college database classes that gave me a solid understanding of databases and their advantages beyond just how to use primary and seondary keys, joins, and so on, so I designed the database tables as flat text files server-side utilizing Boyce-Codd Normal Form (BCNF) (https://en.wikipedia.org/wiki/Boyce%E2%80%93Codd_normal_form) for database table storage organization and optimization.
- I've created many different encryption algorithms and [pseudo] random number generators since there are infinite ways to do so.
- I've coded a spreadsheet web application with cell function functionality matching that of Excel or Google Sheets
- I've created a web desktop/OS using PHP server-side before I learned Node.js that had user management, task/process management and GUIs based on created constraints for the virtual OS, text editor and word processor, file browser/manager that accessed the physical computer's hard drive through PHP (which had to be changed depending on the OS PHP was running on; thank goodness for Node.js), image browser, music player, and limited web browser (depending on if a site would be allowed to run in an iframe call from another domain). I added features like windows movement, minimization/maximization animations, and resize, as well as preference management like desktop background, user information management, and other things emulating a desktop GUI of an OS.

I really wish I still had all of this code to upload to GitHub but most of it has been lost just being stored on my local computers I lost or on websites I stopped paying for hosting, my old GitHub profiles I no longer have access to, and old accounts for Google Drive, Dropbox, or OneDrive I've lost access to. 

**ALWAYS REMEMBER TO UPDATE YOUR PHONE NUMBER WHEN IT CHANGES ON A NEW PHONE WITH A NEW NUMBER FOR TWO FACTOR AUTHENTICATION. CHANGING MY PHONE NUMBER USING A NEW SERVICE PROVIDER ON THE SAME PHONE AFTER LETTING MY CURRENT SERVICE RUN OUT WAS ONE OF THE BIGGEST MISTAKES OF MY _DIGITAL_ LIFE.**

### Sidenote on the Freedom from Dependencies

Most things I remain dependent on but I enjoy working out how to emulate the functionality of any software. When it came to JavaScript in particular I had to be dependent on things due to them being implemented into products where I worked and having experience with them being a benefit when it came to submitting resumes. One of things that really inspired me to dedicate a large majority of my free time to learning and working with only JavaScript, besides it being implemented in browsers and the dependencies being hidden for it to run, was a website called "You Might Not Need jQuery" (https://youmightnotneedjquery.com). I had been using jQuery before working with it as a dependency professionally during my career because at some point in time it became apparent to me that doing a lot of things I wanted to do often had examples written in jQuery. I picked up jQuery because it seemed easy enough to link to in my HTML from a CDN or local file and then I could implement the examples I came across which often had shorter amounts of code and were voted up to the top on sites like StackExchange. I was already **VERY** familiar with CSS before ever really learning JavaScript, even to the point of creating simulated .onclick events using CSS attributes applied to HTML elements like radio buttons (e.g. radio-option::focus .class-i-want-location-of-element-changed-to { top: (#)px; left: (#)px; }). You Might Not Need jQuery encouraged me by showing me examples of many of the common functionalities of jQuery written with just a little more plain JavaScript sometimes in combination of CSS. I read through some of jQuery's source code one day and decided to reverse engineer implementation of the "$" since it seemed easy enough to do, then emulated jQuery's id and class targeting functionality before leaving it at that. 

### Why Web Development Frameworks Were Born and why so Few Exist in My Opinion

...to be continued...
