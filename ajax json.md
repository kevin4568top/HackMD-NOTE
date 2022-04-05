2022-04-05
===
###### tags: `JS紀錄區`
```javascript=
var xhr = new XMLHttpRequest();
xhr.open("get", "url", true); //向伺服器要求甚麼資料
xhr..onreadystatechange = function(){};
xhr.send(); //送出資料
JSON.parse(text); //將text參數的json資料轉為JS物件
JSON.stringify(value); //將value的JS物件轉為json資料
```
```htmlembedded=
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TEST AJAX</title>
    <script type="text/javascript">
        function getData(){
            // XMLHttpRequest 物件專門用來和伺服器做連線
            var req = new XMLHttpRequest();
            // .open(method, url)
            req.open('get', 'http://127.0.0.1:8887/bgd.html');
            req.onload = function() { // load事件，偵測連線的狀態結束
                // 連線完成
                alert(this.responseText);
            }
            req.send(); //送出連線
        }
    </script>
</head>
<body><!--http://127.0.0.1:8887/index.html-->
    <h1> HELLO AJAX </h1>
    <div>
        <span onclick="getData();">BGD</span>
        <span>MLTD</span>
    </div>
    <hr>
    <div class="container"></div>
</body>
</html>
<!-- 點擊BGD即彈出方塊顯示bgd.html的內容-->
![](https://i.imgur.com/BoAM0VL.jpg)

```
```htmlembedded=
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TEST AJAX</title>
    <script type="text/javascript">
        function getData(pageName){
            // XMLHttpRequest 物件專門用來和伺服器做連線
            var req = new XMLHttpRequest();
            // .open(method, url)
            req.open('get', 'http://127.0.0.1:8887/' + pageName);
            req.onload = function() { // load事件，偵測連線的狀態結束
                // 連線完成
                let container = document.getElementById('container');
                container.innerHTML = this.responseText;

            };
            req.send(); //送出連線
        }
    </script>
</head>
<body><!--http://127.0.0.1:8887/index.html-->
    <h1> HELLO AJAX </h1>
    <div>
        <span onclick="getData('bgd.html')">BGD</span>
        <span onclick="getData('mltd.html')">MLTD</span>
    </div>
    <hr>
    <div id="container"></div>
</body>
</html>
<!-- 點擊BGD或MLTD即在下方div容器顯示bgd.html及mltd.html的內容-->
![](https://i.imgur.com/UPcICIS.jpg)

<!--若想要網站在一開啟就載入內容 可在body內加上 onload="getData('bgd.html')"-->

```
```json=
[
    {"book": "SAO",
     "name": "starburst"
    },
    {"book": "BGD",
        "name": "Arisa"
       }
]
```
```htmlembedded=
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AJAX 載入JSON測試</title>
</head>
<body>
    <div id="test"><!-- http://127.0.0.1:8887/json_test.html -->
        AJAX 載入JSON測試
    </div>
<script>
    var xhr = new XMLHttpRequest();
    xhr.onreadystatechange = function(){
        if(this.readyState == 4 && this.status == 200){
            console.log(this.response);
        }
    };
    xhr.open("get", "./test.json", true);
    xhr.send();
</script>
</body>
</html>
<!-- console結果-->
![](https://i.imgur.com/Zyu9bou.jpg)

```
```htmlembedded=
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AJAX 載入JSON測試</title>
</head>
<body>
    <div id="test"><!-- http://127.0.0.1:8887/json_test.html -->
        AJAX 載入JSON測試
    </div>
    <button onclick="btn()">點我</button>
<script>
    function btn() {
        var xhr = new XMLHttpRequest();
    xhr.onreadystatechange = function(){
        if(this.readyState == 4 && this.status == 200){
            document.getElementById("test").innerHTML = this.response;
        }
    };
    xhr.open("get", "./test.json", true);
    xhr.send();
    }

</script>
</body>
</html>
<!-- 按點我後結果-->
![](https://i.imgur.com/60gGUJv.jpg)

```