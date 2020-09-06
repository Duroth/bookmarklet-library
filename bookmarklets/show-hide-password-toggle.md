# Show / Hide Password Toggle

```javascript
javascript:!function(){var t=document.activeElement;t&&"INPUT"==t.nodeName&&("password"===t.type?(t.type="text",t.dataset.is_password=!0):t.dataset.is_password&&(t.type="password"))}();
```

A lot of websites and mobile browsers nowadays place a "show/hide password" button next to password fields
that, when clicked, switches the field between readable text and hidden input (asterisks / dots).
This bookmarklet mimics this functionality, and can be used on just about every website, whether or not
a button is already supplied.

```javascript
(function(){
  var input = document.activeElement; // Get the currently selected element on the page
  if (!(input && input.nodeName=='INPUT')) { return; } // Do nothing if it's not an input field

  if (input.type === 'password') { input.type = 'text'; input.dataset['is_password'] = true; } // Mark as 'text' and store the state;
  else if (input.dataset['is_password']) { input.type = 'password'; } // Or reset the field to 'password' type
})();
```