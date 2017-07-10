# yext
client-side js to operate a Yext API

___

Yext APIs requires client and api keys, and is not CORS enabled. Therefore, a proxy was written to provide the former and circumvent the latter (via  JSONP). The result is a <i>yext.getJSON(url)</i> method that returns a promise.

1. This library can be added to you App by 

```html

<script src=“https://sbm-it.github.io/yext/yext.js”></script>

```

2. and you can call Yext's API with something like

```javascript

yext.getJSON(“https://api.yext.com/v2/accounts/[accountId]/locations?api_key=API_KEY&v=20170710”).then(function(x){console.log(“data retrieved:”,x)})

```

Give it a try in the console of https://sbm-it.github.io/yext. Note how the account id and api_key are handled automatically by the proxy, consumed as <i>[accountId]</i> and <i>api_key=API_KEY</i>.