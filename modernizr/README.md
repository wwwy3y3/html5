# modernizr

modernizr 是一個用來偵測說一個 browser 有支援哪些 html5 和 css3 的規格。 modernizr 的作法很簡單就是回傳一個值告訴你說 client 的 browser 有沒有支援。

modernizr 是用 `navigator.userAgent` 來偵測的。

如果有 browser 沒有支援的規格可以使用 polyfills 來支援。


## modernizr 安裝

modernizr 建議是安裝在 `<head>` 內，且在 css 宣告之後。原因：

- HTML5 Shiv(安裝 HTML5 element 在 IE 中)，需要在 `<body>` 前宣告。
- 如果你用 modernizr 去執行一些 css 的話需要去避免 FOUC 的發生。

## polyfills

是用來彌補瀏覽器不支援的地方，也就是說如果 HTML5 在有些 browser 上不支援的話可以用 polyfills 來補那個漏洞。

[polyfills list](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-browser-Polyfills)，但是在官網上有個警告，也就是說雖然 polyfills 可以解決跨瀏覽器的問題，但是大量的使用 script 會帶來 user 那端的 loading 所以也不是用越多去補會越好。斟酌使用。

資料：

- https://github.com/Modernizr/Modernizr
- https://github.com/Modernizr/Modernizr/tree/master/feature-detects
- https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills
- https://github.com/Modernizr/Modernizr/wiki/Undetectables
- https://github.com/aFarkas/html5shiv
- http://www.paulirish.com/2011/the-history-of-the-html5-shiv/
- http://modernizr.com/docs/