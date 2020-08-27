# GoogleMapSample

1. 將網頁聲明為 HTML5 **`<!DOCTYPE html>`**
2. 創建一個**`div`  id** 為 “ map” 的元素來保存地圖。
3. 定義了一個 JavaScript function 用於在裡面繪製並產生地圖 **`div`**。
4. 使用**`script`** 載入 Maps JavaScript API 。

## 載入 Maps JavaScript API

```jsx
<script defer
  src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap">
</script>
```

**`src`**：從中加載 Maps JavaScript API 的網址，包括使用Maps JavaScript API所需的所有符號和定義。該網址有兩個參數：key，您提供 API 密鑰，和callback，指定 Maps JavaScript API 載入完成後要調用的 function 名稱。
**`defer`**：要求瀏覽器在加載 script 之前先解析 HTML 文檔。執行腳本時，它將調用使用 callback 參數指定的函數。

## 設定地圖/縮放等級/視角

```html
<div id="map"></div>
```

為了使地圖顯示在網頁上，我們必須為其保留一個位置。通常，我們透過 div 元素並在瀏覽器的文檔對像模型（DOM）中獲得對該元素的引用來實現。

每個地圖都有兩個必需的選項：`center` 和 `zoom`。

```jsx
map = new google.maps.Map(document.getElementById('map'), {
  center: {lat: -34.397, lng: 150.644},
  zoom: 8
});
```

通過 `zoom` 屬性設置顯示地圖的初始大小 ，其中 `zoom: 0` 就是整顆地球地圖

`center` 設定視角中心點

宣告經緯度物件

使用 javaScript 宣告經緯度

```jsx
var position = {
          lat: 25.047108,
          lng: 121.542761,
        };
```

或者使用 google 提供的 google.maps.LatLng 物件作儲存

```jsx
var googleLangs2 = new google.maps.LatLng("25.046939", "121.54254");
```

有了經緯度之後， 透過 new google.maps.Marker 就可以產生一個 maker 物件在地圖上

```jsx
var marker = new google.maps.Marker({
          position: googleLangs1,
          map: map,
          animation: google.maps.Animation.BOUNCE
        });
```

`position` 傳入經緯度

`map` 要繪製於哪個 map

`animation` 這個參數可有可無，會有動畫效果 `BOUNCE` : 彈跳 , `DROP` : 掉落

更詳細說明請參考官方網站

[https://developers.google.com/maps/documentation/javascript/overview?hl=zh-tw](https://developers.google.com/maps/documentation/javascript/overview?hl=zh-tw)