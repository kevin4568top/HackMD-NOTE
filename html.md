2022-04-04
===
###### tags: `html紀錄區`

```htmlembedded=
<html>
<head><!--  為告知該頁面的相關資訊   --> 
    <title></title>  <!-- 主題(含在head標籤內) --> 
</head>       

<body><!--下列是含在<body>內的標籤-->
    <h1></h1> ->標體，最多到h6，越後順位字體越小
    <p></p> ->段落
    <b></b> ->粗體字
    <i></i> ->斜體字
    <sup></sup> ->上標 ex:2rd rd會在2上方
    <sub></sub> ->下標 ex:CO2 2會在O下方
    <br /> ->斷行
    <hr /> ->水平線
    <abbr></abbr> ->縮寫，須加上title=""屬性
    <del></del> ->刪除線
    <ins></ins> ->底線
    <ul></ul> ->項目清單，可加type=""
    <ol></ol> ->編號清單，可加type=""
    <li></li> ->清單項目，含在ul或ol內
    <dl> ->定義清單
    <dt> ->要被定義的詞，含在dl內
    <dd> ->用來定義定義詞的元素，含在dl內
    <a></a> ->連結到其他網站，需加href=""
    <a href="mailto:"></a> ->email連結
    <a href="http://www.google.com"    target="_blank">->在新視窗開啟連結
</body>    
</html>    
```
```htmlembedded=
<table>
     <caption>各分店資料列表</caption>
    <tr> <!-- 表頭列 -->
        <th>店名</th>
        <th>地址</th>
        <th>營業時間</th>
    </tr>
    <tr> <!-- 各家分店資訊 -->
        <td>中正店</td>
        <td>台南市中正路100號</td>
        <td rowspan="2">10:00~22:00</td>
    </tr>
    <tr> <!-- 各家分店資訊 -->
        <td>中山店</td>
        <td>台南市中山路30號</td>
                        
    </tr>
    <tr> <!-- 各家分店資訊 -->
        <td>新市店</td>
        <td>台南市新市區新市路2號</td>
        <td>11:00~22:30</td>
    </tr>
    <tr>
        <td></td>
        <td></td>
        <td></td>
    </tr>
</table>
```
```htmlembedded=
 <ol type="I">
    <li><b>統神</b></li>
    <li>國動</li>
    <li><i>拖椅子</i></li>
</ol>
<ul>
    <li>大嘴鳥</li>
    <li>鳥人幫</li>
    <li>小熊維尼</li>
    <li>習維尼</li>        
    <li>哈巴狗</li>
</ul>
<dl>
    <dt>哆啦A夢</dt>
    <dd>胖虎</dd>
    <dt>神鵰俠侶</dt>
    <dd>小龍女</dd>
</dl>
```
```htmlembedded=
<a href="https://www.gamer.com.tw/" target="blank">巴哈姆特</a>
<br>
<img src="images/icon57x57.png" width="200" height="200" alt="這是一張圖片唷">
<br><br><br>
<audio autoplay="autoplay" controls="controls" loop="loop"  preload="auto" id="aud"
       src="music/神魔之塔黑金莉莉絲專屬行動值 BGM.mp3">
     你的瀏覽器版本太低，不支援audio標籤
 </audio>
```
```htmlembedded=
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
<form action="">
    <p>姓名：<input type="text" name="username" placeholder="請輸入姓名" required autofocus></p>
    <p>搜尋：<input type="search" name="search"></p>
    <p>信箱1：<input type="email" name="email"></p>
    <p>信箱2：<input type="text" name="email2" pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,4}$">
    <p>網址：<input type="url" name="url"></p>
    <p>電話：<input type="tel" name="tel"></p>
    <p>數字：<input type="number" name="number" min="1" max="21" step="3"></p>
    <p>日期：<input type="date" name="date"></p>
    <p>時間：<input type="time" name="time"></p>
    <p>程度：<input type="range" name="range"></p>
    <p>顏色：<input type="color" name="color"></p>

    <p><input type="submit" value="送出">
    <input type="reset" value="重置"></p>
</form>
</body>
</html>
```