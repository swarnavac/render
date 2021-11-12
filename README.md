## Browser render: HTML, CSS, JS to DOM

### Scope
This section defines the minimum steps to convert a web file to DOM and render it on a computer screen. It will make knowledge about browsers and help to improve our optimizing skills in developing a web app.

### Purpose
To explain in very simple terms, the steps of the render by browser engine from web files to independent tree DS. It will help up to develop an optimized web app.

### Load the data
We all know that HTML files are loading on the computer in bytes of data (basically a combination of binary digits) from the remote server or perhaps a local disk.

### Intro to Browser Engine
Browser engine handles the process after loading.
The browser engine is the core software component of a web browser. It traverses the HTML files into DOM.

Every browser has its own browser engine.
For example:
- Google created Blink engine for its Chrome browser.
- Mozilla created Gecko for its Firefox browser.
- Apple created WebKit for its Safari browser.
- Microsoft created Trident and EdgeHTML for its Internet Explorer and Edge respectively.
- Opera has Presto.
- Linux Foundation has Servo. (Experimental)

### HTML TO DOM
The browser engine converts the bytes of data (HTML files) into characters.
Through tokenization, characters are converted into tokens and the tokens are then converted into nodes.
Using the nodes, the browser engine creates an independent tree data structure where each node treats as an object, this tree data structure is called DOM or Document Object Model.

For example:
Assume that there are two children of a parent in a tree one is the left child another is the right child.
So, the code must be like the following before conversion.
```
<parent>
	<left_child></left_child>
	<right_child></right_child>
</parent>
```
The algorithms work like that. It creates a tree data structure through these tags (angle brackets).
### CSS to CSSOM
Similarly, for CSS files browser engine converted CSS files into characters, then characters to tokens, tokens to nodes. Then nodes to CSSOM (Cascading Style Sheets Object Model).
CSS converts to CSSOM exactly after HTML to DOM. It helps to style the web page.

> DOM and CSSOM both are independent tree data structures.

### Render tree by DOM & CSSOM
For rendering the browser engine combines the two independent tree data structures (DOM and CSSOM) into one and make a render tree.
 > If an element is hidden by CSS property (display: none) then that element is not added to this render tree from DOM.

![DOM + CSSOM = Render tree](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/images/render-tree-construction.png)

### Layout
From the render tree, the browser creates a layout after determining the size and position of each and every visible element.
A new layout will be created whenever javascript modify the elements of the render tree.

### Paint
Now according to the layout browser prints the elements on the screen, and we get to see and enjoy them.

### Quick Recap
- Process HTML and build DOM tree.
- Process CSS and build CSSOM tree.
- Combine DOM and CSSOM into render tree.
- Make layout from render tree.
- Paint each element to the screen.

### Conclusion
It is important to write HTML code in an optimized way, that browser engine will take minimum time to create a low complexity tree. Also, reduce the time between initial render and updates.

### References
- https://blog.logrocket.com/how-browser-rendering-works-behind-scenes/
- https://glenelkins.medium.com/the-secrets-of-the-cssom-why-you-should-care-943a1d50307b/
- https://www.youtube.com/watch?v=gh7GRSkIkLM/
