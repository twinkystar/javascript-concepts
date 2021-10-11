# Script loading 
First -HTML then JS. else, error

#### 1 ) In inline <script> tag is between <head> causes error hence we use

  ```js
  document.addEventListener("DOMContentLoaded", function() {
  ...
});
  ```
This is an event listener, which listens for the browser's "DOMContentLoaded" event, which signifies that the HTML body is completely loaded and parsed. The JavaScript inside this block will not run until after that event is fired, therefore the error is avoided 

#### 2 ) In external - we use “defer” attribute as -ORDERED loading of 1+ scripts

  ```js
  <script src="script.js" defer></script>
  ```
which tells the browser to continue downloading the HTML content once the <script> tag element has been reached. BUT execute after HTML

#### 3) Or use “async” attribute - download 1+ script(s)  asynchronous (any order) w/o blocking rendering of page and will execute it as soon as the script finishes downloading. - SCRIPTS MUST BE INDEPENDENT
```js
  <script async src="js/script3.js"></script>
  ```
#### 4 ) In old-fashioned solution, put <script> tag just before </body> tag (so that it would load after all the HTML has been parsed) - cause performance issue though.

## To summarize:
  
async and defer both instruct the browser to download the script(s) in a separate thread, while the rest of the page (the DOM, etc.) is downloading, so the page loading is not blocked by the scripts.
If( scripts - run immediately + no  dependencies) → use async. //parsed + exec immediate
If(scripts - wait for parsing + dependent on other scripts + the DOM being in place) → defer and put <script> tag in order. //parsed with HTML + exec after HTML
