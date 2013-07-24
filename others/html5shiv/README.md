# html5 shiv

他的概念是去處理， IE 上面無法去辨識 HTML5 的標籤問題，因為 HTML5 在 IE 上面還有很多支援的問題，所以如果 IE 上面無法辨識這個標籤，那麼 css 去指定的那個標籤外觀會是無效的

例如：

```
<html>
    <head>
        <style>blah { color: red; }</style>
    </head>
    <body>
        <blah>Hello!</blah>
    </body>
</html>
```

因為 IE 看不懂 blah 這個標籤，所以他的顏色不會變成紅色。
於是有個人叫做  Sjoerd Visscher 提出一個[想法](http://intertwingly.net/blog/2008/01/22/Best-Standards-Support#c1201006277)，也就是用 `document.createElement(elementName)`，這樣的方式讓 IE 認識這個標籤。

```
<html>
    <head>
        <style>
          figure { border: 1px inset #AAA; padding: 4px; }
        </style>
        <script>document.createElement("figure");</script>
    </head>
    <body>
        <figure>
          <img src="http://ejohn.org/files/jeresig-wordpress-sm.jpg"/>
        </figure>
    </body>
</html>
```

以上面的例子， IE 就會去認識 figure 這個標籤了。

資料：

- https://github.com/aFarkas/html5shiv
- http://www.paulirish.com/2011/the-history-of-the-html5-shiv/
- http://xopus.com/devblog/2008/style-unknown-elements.html
- http://remysharp.com/2009/01/07/html5-enabling-script/
- http://ejohn.org/blog/html5-shiv/