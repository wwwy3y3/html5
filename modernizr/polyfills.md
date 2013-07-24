## polyfills

`polyfills` 是去處理那些比較舊的 browser 所不支援的 function 所提出來的概念。也就是說 `polyfills` 是用來支援有關新 browser 有的功能而舊 browser 所不支援的地方，用 `polyfills` 來補足。

這裡有篇提出這個概念的人寫的文章，[What is a polyfills?](http://remysharp.com/2010/10/08/what-is-a-polyfill/)

pollyfills 的概念就是

> A shim that mimics a future API providing fallback functionality to older browsers.


## 寫 polyfills

雖然我本身沒有寫過 polyfills 但是這裡有篇不錯的文章推薦給大家 [Writing polyfills](http://addyosmani.com/blog/writing-polyfills/)


## 如何使用 polyfills 

很多人都是用 yepnope 來加上 Modernizr 來判斷說他的 browser 有沒有支援有的話就不跑 polyfills ，沒的話就去跑 polyfills 補足。


Modernizr 有篇 wiki 專門寫他們有收集到的 polyfills 還滿實用的 [HTML5 Cross Browser Polyfills](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-browser-Polyfills)