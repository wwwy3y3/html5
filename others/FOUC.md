# FOUC(Flash of unstyled content)

## FOUC

這個現象是因為 `@import` 的時候 IE 會有 a momentary flash of unstyled page content 這個問題，也就是他會有一段時間不會去載入 css stylesheet

測試：http://www.bluerobot.com/web/css/fouc.asp/ 在這個網站內可以做 FOUC 的測試。

## FOUC 原因

```
<head>
    <title>My Page</title>
    <style type="text/css" media="screen">@import "style.css";</style>
</head>
```

`<style type="text/css" media="screen">@import "style.css";</style>` 這行的原因所以造成了這個現象。

## solution

### LINK element 

```
<head>
    <title>My Page</title>
    <link rel="stylesheet" type="text/css" media="print" href="print.css">
    <style type="text/css" media="screen">@import "style.css";</style>
</head>
```


### SCRIPT element

```
<head>
    <title>My Page</title>
    <script type="text/javascript"> </script>
    <style type="text/css" media="screen">@import "style.css";</style>
</head>
```


資料：

- http://www.bluerobot.com/web/css/fouc.asp/
- http://www.paulirish.com/2009/avoiding-the-fouc-v3/
- http://en.wikipedia.org/wiki/Flash_of_unstyled_content
- http://www.learningjquery.com/2008/10/1-way-to-avoid-the-flash-of-unstyled-content
- https://www.webkit.org/blog/66/the-fouc-problem/