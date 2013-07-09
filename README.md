Firebase Sample Chrome Extension
================================
This is a demonstration of using Firebase in a Chrome extension.

Extension Usage
-----
Installing the extension adds an icon next to the chrome address bar, which when clicked opens a popup that displays the number of times the icon has been clicked (by all users of the extension).

![Screenshot](http://firebase.github.io/external_images/firebase-chrome-extension.png)


Using Firebase in an Extension
------------------------------
The key to using Firebase in a Chrome extension is adding the following content security policy to your manifest.json:

```json
{
  "content_security_policy": "script-src 'self' https://cdn.firebase.com https://*.firebaseio.com; object-src 'self'"
}
```

Note that:

1. You must use the wildcard domain (https://*.firebaseio.com not https://yourfirebase.firebaseio.com), since internally Firebase may need to connect to other subdomains.
2. You must use https:// when including firebase.js and when referencing any Firebase URLs, since Chrome extensions don't allow http script includes.

Once you've done that, you can use Firebase just as you would in any other web app.  See our [Getting Started](https://www.firebase.com/docs/) guide for details.

License
-------
[MIT](http://firebase.mit-license.org/).
