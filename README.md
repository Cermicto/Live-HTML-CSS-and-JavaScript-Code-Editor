# Live HTML, CSS, and JavaScript Code Editor

Runs online or offline.

Hosted at: https://powerfulillusion.com/live-html-css-js-editor/

## Project Goal: Build an online live HTML/CSS/JavaScript code editor like Codepen that updated a webpage as you typed

This project builds upon my previous experiences in reverse-engineering syntax highlighting, working with textareas, and utilizing iframes.

## What it Ultimately Does

**The gist of it**: Captures the HTML, CSS, and JavaScript code on keyup events, displays highlighted syntax, and combines the HTML, CSS, and JavaScript for output to an iframe while running the JavaScript within the iframe.

## Details on Learning How to Create / Reverse Engineer the Different Parts

### The Full Web Application Initial Approach

I read from several sources that some online HTML/CSS/JavaScript editors were based on a project called CodeMirror (https://codemirror.net). It seemed like a great starting point and is arguably a quicker option for implementing functionality like displaying code with syntax highlighting. I went through the documentation, examined many examples from the CodeMirror repository, and eventually thought:
"This would be easier and more fun to reverse engineer. At the very least, I could fully understand my product and maintain it easily without dependencies."
(Note: I didn’t reverse-engineer CodeMirror entirely—just created the functionality I was looking for.)

While I appreciate dependencies when I need complex operations performed under time constraints, I’m always eager to write the code myself to learn and fully understand what I’m doing. There are countless inventions in software that I'm **SO THANKFUL** for—like operating systems, web browsers, and the Internet. I wish I could discuss anything, including their inventions, with every creator involved.

### Syntax Highlighting

In the past, I’ve explored various methods for implementing syntax highlighting in web-based text editors. While my methods may resemble existing implementations, I never researched how to do it directly, opting instead to reverse-engineer the process.

Initially, I used a textarea or a contenteditable HTML element to capture text and replaced specific characters with HTML span elements, applying classes for syntax highlighting. This processed HTML was then displayed within an element’s .innerHTML. At first, I maintained two separate areas: one with a contenteditable HTML element and one for the highlighted HTML. Both approaches worked for capturing inner text or HTML.

However, I eventually realized that using a textarea would simplify retrieving line numbers—a feature required for my code editor. The final implementation uses transparent textarea elements for HTML, CSS, and JavaScript editor areas, keeping the cursor visible. On keyup, the value of the textarea is processed into HTML with span tags for styling, which is then displayed in an underlying div element. The textarea and div are styled with matching font-size, line-height, and other properties to align the text and cursor.

### Reverse Engineering and Creating Emulators is the most Fun and Valuable Learning Experience in my Opinion

I've learned a great deal by reverse-engineering or emulating software applications and hardware functionality. Here are a few examples:

- I programmed a virtual CPU with registers and created an assembly language interpreter in JavaScript.
- I developed a database using Node.js API endpoints and local file storage. It accepted standardized REST API calls and even encrypted SQL SELECT statements sent via AJAX. I designed server-side database tables using Boyce-Codd Normal Form (BCNF) for optimized storage.
- I created encryption algorithms and [pseudo] random number generators.
- I built a spreadsheet web application with cell functionality similar to Excel or Google Sheets.
- I coded a PHP-based web desktop/OS before learning Node.js, featuring user management, task management, GUIs, file browsing, text editing, and more.

Unfortunately, much of this code has been lost due to hosting lapses, outdated devices, and inaccessible accounts.

**ALWAYS REMEMBER TO UPDATE YOUR PHONE NUMBER FOR TWO-FACTOR AUTHENTICATION. NOT DOING SO WAS ONE OF MY BIGGEST DIGITAL MISTAKES.**

### Sidenote on the Freedom from Dependencies

While I’m dependent on many things (e.g., operating systems, browsers), I enjoy emulating software functionality. My journey with JavaScript dependencies began professionally, but a website called You Might Not Need jQuery inspired me to focus on plain JavaScript. The site demonstrated how many common jQuery functionalities could be replicated with minimal JavaScript and CSS.

Reading through parts of jQuery’s source code motivated me to emulate its $ functionality and targeting mechanisms, further enhancing my understanding of JavaScript’s potential.
