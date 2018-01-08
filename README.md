# copyOnClick
A sample Javascript that allows to click on an element to copy content to the local clipboard.

## Usage
Create elements so that they have a class of "click-to-copy" and an attribute data, which will contain the string copied to the clipboard when the element is clicked onto:

```html
<h2 class="click-to-copy" data="first">Click me to copy "first" into your clipboard</h2>
<h2 class="click-to-copy" data="second">Click me to copy "second" into your clipboard</h2>
```

The sample (index.html) attaches copyToClipboard() to every element of class "click-to-copy":

```Javascript
// Attach onclick event to all the element with "click-to-copy" class
const clickToCopyElements=document.querySelectorAll(".click-to-copy")
for (var e=0; e < clickToCopyElements.length; e++) {
    clickToCopyElements[e].onclick = copyToClipboard
}
```


Besides copying the data payload to the clipboard, the function also briefly displays a visual clue that the copy happened:
```Javascript
// Set up screen element(s)
//...
document.querySelector("body").appendChild(screen)
setTimeout(() => { screen.remove() },1000)
```
