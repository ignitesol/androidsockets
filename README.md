# AndroidSockets

This library tries to emulate simple bare-minimum websocket functionality for android webview.

## Usage

You will need to set up AndroidSockets in the activity as well as in the WebView. 

#### WebView

AndroidSocket can be set up in the webview by simply including `androidsockets.js` in
your html file.

```
    <script type="text/javascript" src="/path/to/androidsockets.js"></script>
```

#### Activity

AndroidSockets uses [WebViewCommunicator](https://github.com/ignitesol/webview-communicator), for communcating with the WebView. Assuming
you have an instance of WebViewCommunicator you can set up AndroidSockets by simply
creating an AndroidSockets object

```
    webInterface = new WebViewCommunicator(myWebView, myHandler);
    AndroidSockets aSocket = new AndroidSockets(webInterface);
```

OR

If you are not using WebViewCommunicator, you can set up AndroidSockets as follows

```
    AndroidSockets socket = new AndroidSockets(myWebView, new android.os.Handler());
```

where myWebView is the WebView in which you need to emulate WebSocket.

The above setup will insert a dummy WebSocket object in Javascript. Now rest of your code can simply use WebSockets as you would in a normal browser.

## Credits

AndroidSockets uses [WebSocket client for Android](https://github.com/codebutler/android-websockets) (Copyright (c) 2012 Eric Butler).

