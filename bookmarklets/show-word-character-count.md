# Show Word / Character Count

```javascript
javascript:!function(){var e,n=document.activeElement,t=document.getSelection();if(!n||"INPUT"!=n.nodeName&&"TEXTAREA"!=n.nodeName){if(!t.length)return;e=t}else e=n.value;var o=e.length,l=e.split(/\s+/).length;window.alert(`Word count: ${l}\nChar count: ${o}`)}();
```

Worried about hitting an invisible maximum character or word count when typing?  Want to shorten some text
to hit that SEO sweet spot for meta descriptions? This bookmarklet shows the word and character count
for the input element you're currently typing in, or the text you currently have selected on the webpage.

```javascript
(function(){
    var txt;
    var activeEl = document.activeElement; // Get the currently selected element on the page
    var selection = document.getSelection(); // Get the currently selected text on the page
    if (activeEl && (activeEl.nodeName == 'INPUT' || activeEl.nodeName == 'TEXTAREA')) {
        txt = activeEl.value; // If the selected element is an input of some kind, grab its contents as the marked text
    } else if (selection.length) {
        txt = selection; // Otherwise, grab the selected text on the page
    } else {
        return; // If neither of the above apply, skip the rest of the function.
    }

    var clen = txt.length; // Character length: Number of individual characters in the string.
    var wlen = txt.split(/\s+/).length; // Word count: Approximated by splitting on whitespace and counting the items.

    window.alert(`Word count: ${wlen}\nChar count: ${clen}`); // Tell the values through an alert window.
})()
```