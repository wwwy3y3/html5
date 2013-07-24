# 處理不支援 js 的 client

Paul Irish 在一篇的 blog 上分享了他如何 deal with 沒有使用 js 的使用者的方式。

``` 
<html class="no-js">
    <head>
        <script>(function(H){H.className=H.className.replace(/\bno-js\b/,'js')})(document.documentElement)</script>
```

先把 html 設定一個 class 為 `no-js` 這樣如果他沒有跑 script 裡面的 code 的話他的 class 為 no-js 所以會去用 no-js 的 css code。

而如果他支援 js 的話會去啟動

```
document.documentElement.className = document.documentElement.className.replace(/\bno-js\b/,'js');
```

這行 script 會把 no-js 換成 js。換成 js 後就可以去跑 js class 的 css。



資料：

- http://www.paulirish.com/2009/avoiding-the-fouc-v3/