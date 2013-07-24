## html5 

html5 並不是什麼非常新的技術，在維基百科上就可以查得 " HTML 5 草案的前身名為 Web Applications 1.0 ，是在 2004 年由 WHATWG 提出，再於 2007 年獲 W3C 接納" 。所以之所以他很普遍所以也對開發者來說非常重要，需要花點時間去了解。

用了 html5 你也不需要把你 html4 裡面的語法丟掉，因為他們有很好的整合。完全的兼容。


## 使用 html5
 
``` html

<!DOCTYPE html>

```

把這個放在整個網站的最上面，就可以使用 html5 的語法了，簡單吧！


## MIME types


> 多用途網際網路郵件擴展（MIME，Multipurpose Internet Mail Extensions）是一個網際網路標準，它擴展了電子郵件標準，使其能夠支持非ASCII字元、二進制格式附件等多種格式的郵件消息。
（來源自 [wikipedia](http://zh.wikipedia.org/wiki/%E5%A4%9A%E7%94%A8%E9%80%94%E4%BA%92%E8%81%AF%E7%B6%B2%E9%83%B5%E4%BB%B6%E6%93%B4%E5%B1%95)）

mime types 之所以重要的原因是每次你的 browser 送一次 request 給 server 的時候， server 都會傳一個 header 給 browser 說他回傳的資料形式是什麼。


### 內容類型

``` html

Content-Type: [type]/[subtype]; parameter

```

#### type 形式：

- Text：用於標準化地表示的文本信息，文本消息可以是多種字符集和或者多種格式的

- Multipart：用於連接消息體的多個部分構成一個消息，這些部分可以是不同類型的數據

- Application：用於傳輸應用程序數據或者二進制數據

- Message：用於包裝一個E-mail消息

- Image：用於傳輸靜態圖片數據

- Audio：用於傳輸音頻或者音聲數據

- Video：用於傳輸動態影像數據，可以是與音頻編輯在一起的視頻數據格式。

#### subtype:

- text/plain（純文本）

- text/html（HTML文檔）

- application/xhtml+xml（XHTML文檔）

- image/gif（GIF圖像）

- image/jpeg（JPEG圖像）【PHP中為：image/pjpeg】

- image/png（PNG圖像）【PHP中為：image/x-png】

- video/mpeg（MPEG動畫）

- application/octet-stream（任意的二進制數據）

- application/pdf（PDF文檔）

- application/msword（Microsoft Word文件）

- application/vnd.wap.xhtml+xml (wap1.0+)

- application/xhtml+xml (wap2.0+)

- message/rfc822（RFC 822形式）

- multipart/alternative（HTML郵件的HTML形式和純文本形式，相同內容使用不同形式表示）

- application/x-www-form-urlencoded（使用HTTP的POST方法提交的表單）

- multipart/form-data（同上，但主要用於表單提交時伴隨文件上傳的場合）

（來源自 [wikipedia](http://zh.wikipedia.org/wiki/%E5%A4%9A%E7%94%A8%E9%80%94%E4%BA%92%E8%81%AF%E7%B6%B2%E9%83%B5%E4%BB%B6%E6%93%B4%E5%B1%95)）

### 內容編碼

``` html

Content-Transfer-Encoding: [mechanism]

```


也就是 MIME type 的原因，client 才知道他所接收到的訊息是什麼格式。