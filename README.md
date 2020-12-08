# safarivarurl
Example showing safari var bug

Open index.html in Chrome, you'll see a background.

In Safari, not so much.

It *seems* that while the css is loaded from css/, the fallback path isn't processed relative to that.

In Chrome, the url fallback in this this:

    background-image:var(--alternatebackground, url(../img/background.jpg));

is processed relative to the CSS path, as expected.

In Safari, it is processed relative to the html page that loaded it, like JavaScript.

This means that when loaded in a subfolder, say safarivarurl/index.html these URLs are loaded:

Chrome: safarivarurl/img/background.jpg
Safari: img/background.jpg

WAT