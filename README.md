# Race Condition in HTML DOM Manipulation

This repository demonstrates a race condition that can occur when JavaScript attempts to manipulate the DOM before the HTML element it's targeting is fully parsed by the browser.  The issue is especially pronounced in older or less-compliant browsers.

## The Bug
The `bug.html` file contains a simple HTML structure with a `<div>` element.  A JavaScript script attempts to add more content to this div using `innerHTML`.  If the script runs *before* the `<div>` element is fully parsed by the browser, it will result in an error because the element may not yet exist in the DOM.

## The Solution
The `solution.html` file offers two ways to fix this race condition:

1. **Placing the script at the end of the body:** This ensures the script executes only after the entire HTML document is parsed.
2. **Using `DOMContentLoaded` event:** This approach uses the `DOMContentLoaded` event listener, which ensures the script executes only when the DOM is ready.

This is a subtle but important issue in web development, especially when dealing with complex websites or libraries that perform extensive DOM manipulation.