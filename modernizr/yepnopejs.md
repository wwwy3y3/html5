## yepnope.js

就是一個 javascript 的 module loader，非常簡單和快速的 module loader。

``` javascript

yepnope({
    load: ["https:/­/my-cdn.com/jquery.min.js?v=1.7.1", "https:/­/my-cdn.com/jquery-ui.min.js?v=1.8.16"],
    callback: {
        "jquery.min.js": function () {
        console.log("jquery loaded!");
    },
        "jquery-ui.min.js": function () {
        console.log("jquery-ui loaded!");
    }
    }
});

```

看上面的這個範例可以看到，他會先去跑 `jquery.min.js` 然後同時跑 `jquery-ui.min.js`，同時跑的原因就是因為他這個 module loader 是用非同步的 load modules 進來。


![yepnope logo](./img/logo/yepnope.jpg "yepnope logo")

----

## 為什麼要使用 yepnope

yepnope 可以用最快的速度去用非同步和平行處理的方式去載入你要的 js, css 檔。為什麼不要把它像傳統一樣直接全部載入的原因是因為 yepnope 這樣非同步處理的方式會比傳統上的方式快很多。

----

## yepnope 的 API

``` javascript

yepnope([{
    test : /* boolean(ish) - Something truthy that you want to test             */,
    yep  : /* array (of strings) | string - The things to load if test is true  */,
    nope : /* array (of strings) | string - The things to load if test is false */,
    both : /* array (of strings) | string - Load everytime (sugar)              */,
    load : /* array (of strings) | string - Load everytime (sugar)              */,
    callback : /* function ( testResult, key ) | object { key : fn }            */,
    complete : /* function                                                      */
}, ... ]);

```

yepnope 可以去跑 js, css 檔 include 進來。

看上面的 API 可以看到他如果他的 test 跑完後如果是 true 的話會跑 yep, 如果是 false 的話會跑 nope。

跑 test 通常都是去跑 `Modernizr` 的 API。

後面我在寫篇有關 Modernizr 的運用。

``` javascript

yepnope({
    test: Modernizr.geolocation,
    yep: 'regular-styles.css',
    nope: ['modified-styles.css', 'geolocation-polyfill.js'],
    callback: function (url, result, key) {
        alert(url);
    }
});

```

Modernizr.geolocation 這就是 Modernizr 的 test 如果他可以去執行這個 function 的話會跑 yep, 如果不行就跑 nope，跑完後跑 callback。

如果他跑 nope 的話可以讓他去跑一些 [Polyfills](/html5/polyfills/2013/06/26/polyfills.html) (也就是一些專門支援舊版本不支援新版本的 browser，讓他們能夠去支援這些 function)

就這樣簡單介紹。

剩下的細節請自行去他的官網看。

