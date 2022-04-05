2021-12-27~2022-04-01
===
###### tags: `css紀錄區`
```css=
    /*全域選擇器, 選擇html內所有元素*/
* { 宣告;}

    /*元素選擇器*/
body {
}
/*Class選擇器*/
.class {
    
}
/*id選擇器*/
#id {
    
}
```
```css=
color:;
background-color: ;
opacity: ; /*透明度 0~1.0*/
font-family: ; /*字型*/
font-size: ;
font-weight: bold ; /* 粗體*/
font-style: italic ; /*斜體*/
line-height: ; /*行高*/
text-shadow: 水平位移距離 垂直位移距離 模糊長度(px) 顏色 ;

border: 上,右,下,左;
padding: 上,右,下,左 ; /*內距，元素內容與外框之間的距離*/
margin:  上,右,下,左 ; /* 邊界，外框與其他區塊元素的距離*/
display: ; /* 將行內元素轉為區塊層級元素 inline / block / inline-block / none */
border-radius: 左上 右上 右下 左下 ; /*圓角*/
cursor: url(""); /*游標樣式*/

```
```css=
/*position*/
position:static ; /* 正常流向 不指定顯示位置*/
position:relative ; /* 相對定位 以元素現在位置為基準點來指定位置*/
position:absolute ; /* 絕對定位 以元素的父層元素有設定position基準為基準起始點來指定位置*/
position:fixed ; /* 固定定位 以瀏覽器畫面的左上角為基準點來指定位置*/

z-index: ; /*重疊元素*/
float: ; /*浮動元素*/
clear: ; /*淨空浮動元素 left / right / bith / none */
```
```htmlembedded=
<!DOCTYPE html>
<html>
    <head>
        <title>CSS_animation</title>
        <style>
            h1 {
                color: blue;
                font-size: 22px;
                text-align: center;
            }
            body {
                background-image: url();
                background-repeat: no-repeat; /* 背景圖不重複 */
                background-position: center center;
                height: 500px;
                animation: moving /* 動畫名稱 */ 
                           5s /* animation-duration */ 
                           linear /* 播放速度 */
                           infinite /* 循環播放 */;
            }
            @keyframes moving {/* 動畫物件宣告 */
                /* 將背景圖從最左到最右 */
                /*from {background-position: left} to {background-position: right};*/
                0%{background-position: 0%}
                50%{background-position: 100%}
                100%{background-position: 0%}
            }
            .div1 {
                width: 500px;
                height: 300px;
                background-color: grey;
                position: relative;
                left: 10px;
                top: 320px;
            }
            h3 {
                width: 100px;
                height: 50px;
                
                
                position: absolute;
                animation: h3-moving 10s linear infinite;
                 
             }
            @keyframes h3-moving {
                0% {left: 0px; top: 0px; color: blue; background-color: azure;}
                25% {left: 400px; top: 0px; color:brown; background-color:chartreuse;}
                50% {left: 0px; top: 220px; color: yellow; background-color: darksalmon;}
                75% {left: 400px; top: 220px;color: deeppink; background-color: red;}
                100% {left: 0px; top: 0px;color: blue; background-color: azure;}
            }
            .div2 {
                width: 500px;
                height: 300px;
                background-color: bisque;
                position: relative;
                left: 10px;
                top: 280px;
                
            }
            img {
                width: 100px;
                height: 100px;
                position: relative;
                animation-name: img-moving;
                animation-duration: 5s;
                animation-iteration-count: infinite;
                animation-direction: alternate;
            }
            @keyframes img-moving {
                0% {left: 0px; top: 0px; width: 100px;}
                25% {left: 400px; top: 0px; width: 50px;}
                50% {left: 400px; top: 200px; width: 75px;}
                75% {left: 0px; top: 200px; width: 50px;}
                100% {left: 0px; top: 0px; width: 100px;}
            }
        </style>
    </head>
    <body>

    <h1>CSS_animation</h1>
    <hr>
        <section>
           <h2>此範例為將背景圖進行動畫移動</h2>
        </section>
        <section>
            <div class="div1">
                <h3>文字動畫移動</h3>
            </div>
        </section>
        <section class="sec3">
            <h2>圖案動畫及方向移動</h2>
            <div class="div2">
                <img src="images/online.png">
            </div>
        </section>
    </body>
</html>
```
```htmlembedded=
<!DOCTYPE html>
<html>
    <head>
        <title>CSS_animation圖表實例</title>
        <style>
            h1 {
                color: blue;
                font-size: 22px;
                text-align: center;
            }
            ol {
                border: 2px dotted orange;
            }
            li { /* 項次樣式 */
                margin: 3px;
                width: 8em;
                border-right-style: solid; /* 右框線 */
                border-right-color: red;
            }
            @keyframes bar1 { /* 第一直條-html */
                from {border-right-width:0px;}
                to {border-right-width:150px;}
            }
            @keyframes bar2 { /* 第二直條-css */
                from {border-right-width:0px;}
                to {border-right-width:100px;}
            }
            @keyframes bar3 { /* 第三直條-js */
                from {border-right-width:0px;}
                to {border-right-width:50px;}
            }
            .htm {
                animation: bar1 2s linear infinite;
                border-right-width: 150px;
            }
            .css {
                animation: bar2 1.5s linear infinite;
                border-right-width: 100px;
            }
            .js {
                animation: bar3 1s linear infinite;
                border-right-width: 50px;
            }
        </style>
    </head>
    <body>

    <h1>CSS_animation圖表實例</h1>
    <hr>
    <h3>最受歡迎的網頁程式語言</h3>
    <ol>
        <li class="htm">HTML:150票</li> 
        <li class="css">CSS:100票</li> 
        <li class="js">JS:50票</li> 
    </ol>
    </body>
</html>
```
```htmlembedded=
<!DOCTYPE html>
<html>
    <head>
        <title>CSS_Transition轉移特效</title>
        <style>
            h1 {
                color: blue;
                font-size: 22px;
                text-align: center;
            }
            section {
                height: 150px;
                background-color: azure;
                color: #fff;
                font: 600 14px/24px;
            }
            .box1 {
                background-color: #2db34a;
                border-radius: 6px;
                cursor: pointer; //游標
                height: 95px;
                line-height: 95px;
                text-align: center;
                width: 95px;
                transition-property: background;
                transition-duration: 2s;
                transition-timing-function: linear;
            }
            .box1:hover {
                background: #ff7b29;
            }
            .box2 {
                background-color: #2db34a;
                border-radius: 6px;
                cursor: pointer; //游標
                height: 95px;
                line-height: 95px;
                text-align: center;
                width: 95px;
                transition-property: background, border-radius;
                transition-duration: .5s, 1s;
                transition-timing-function:linear;
            }
            .box2:hover {
                background: deeppink;
                border-radius: 50%;
            }
            .box3 {
                background-color: gray;
                border: 1px solid;
                border-radius: 6px;
                cursor: pointer; //游標
                height: 95px;
                line-height: 95px;
                text-align: center;
                width: 95px;
                /* 使用transition對 hover active以shorthand(縮寫) */ 
                transition: box-shadow 1s, background-color 1s, filter 2s, font-size 1s;
            }
            .box3:hover {
                box-shadow: 5px 5px 20px 5px rgba(0,0,0,0,5);/* 陰影 */
                filter: brightness(1.5);
                font-size: 30px;
            }
            .box3:active { /* 被點擊 */
                background-color: red;
                opacity: 0.8; /* 透明度 */
            }
        </style>
    </head>
    <body>

    <h1>CSS_Transition轉移特效(偽類[hover,active])</h1>
    <hr>
        <section>
            <div class="box1">Box1</div>
        </section>  
        <section>
            <div class="box2">Box2</div>
        </section> 
        <section>
            <div class="box3">Box3</div>
        </section> 
    </body>
</html>
```
```htmlembedded=
<html>
    <head>
        <meta charset="utf-8">
        <title>CSS基礎_色彩漸層樣式屬性</title>
        <style>
            h1 { /* 標題文字樣式 */
                color: blue;
                font-size: 26pt;
                text-align: center;
            }
            /* 線性漸層 */
            #ex1 {
                background: linear-gradient(red, yellow);/* 預設上->下 */
            }
            #ex2 {
                background: linear-gradient(to right , yellow, blue);/* 預設左->右 */
            }
            #ex3 {
                background: linear-gradient(to left , blue, white 30%, green);/* 預設右->左 */
            }
            #ex4 {
                background: linear-gradient(to top , red, green);/* 預設下->上 */
            }
             #ex5 {
                width: 150px;
                height: 150px;
                background: linear-gradient(to top right, green, yellow 30%, red);/* 預設左下->右上 */
            }
            /* 部分區段漸層 */
            section#sec8 {
                 background: linear-gradient(to right bottom, yellow, gray);/* 區段 */
            }
            h2#ex6 {
                 background: linear-gradient(to right, yellow, red);
            }/*單一標題*/
            p#pex7 {/* 單一段落 */
                 background: linear-gradient(to right, blue, pink, yellow);
                 color: white;
            }
            /*放射性漸層*/
            h2#rex1 {
                background: radial-gradient(red, yellow, green);/* 預設圓形 */
            }
            h2#rex2 {
                background: radial-gradient(ellipse, yellow, blue); /* 橢圓形*/
            }
             h2#rex3 {
                 width: 200px;
                 height: 100px;
                background: radial-gradient(circle closest-side, white, red 60%, gray); /* 橢圓形*/
            }
             h2#rex4 {
                 width: 200px;
                 height: 100px;
                background: radial-gradient(ellipse farthest-side, white, red 60%, gray); /* 橢圓形*/
            }
            /* 重複性漸層 */
            #rpex1 {
                background: repeating-linear-gradient(to right, yellow 0%, orange 20%);
            }
            #rpex2 {
                background: repeating-linear-gradient(to top right, red 0%, white 25%, blue 50%);
            }
            #rpex3 {
                background: repeating-radial-gradient(orange, yellow 20px, orange 40px);
            }
            #rpex4 {
                background: repeating-radial-gradient(circle, red, yellow, lightgreen 100%, yellow 150%, red 200%);
            }
        </style>
    </head>
    <body>
        <header>
            <h1>CSS基礎_色彩漸層樣式屬性</h1>
            <hr>
        </header>
        <main>
            <section>
                <h3>線性漸層 linear-gradient</h3>
                <h2 id="ex1">CSS 線性漸層1</h2>
                <h2 id="ex2">CSS 線性漸層2</h2>
                <h2 id="ex3">CSS 線性漸層3</h2>
                <h2 id="ex4">CSS 線性漸層4</h2>
                <h2 id="ex5">CSS 線性漸層5</h2>
            </section>
            <section id="sec8">
                <h2 id="ex6">部分區段漸層(標題)</h2>
                <p id="pex7">部分區段漸層文字linear-gradient partlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradientlinear-gradient</p>
            </section>
            <section>
                <hr>
                <h3>放射性漸層 linear-gradient</h3>
                <h2 id="rex1">CSS 放射性漸層1</h2>
                <h2 id="rex2">CSS 放射性漸層2</h2>
                <h2 id="rex3">CSS 放射性漸層3</h2>
                <h2 id="rex4">CSS 放射性漸層4</h2>
            </section>
            <section>
                <hr>
                <h3>重複性漸層 linear-gradient</h3>
                <h2 id="rpex1">CSS 重複性線性漸層1</h2>
                <h2 id="rpex2">CSS 重複性線性漸層2</h2>
                <h2 id="rpex3">CSS 重複性放射性漸層3</h2>
                <h2 id="rpex4">CSS 重複性放射性漸層4</h2>
            </section>
        </main>
        <footer>
        </footer>
    </body>
</html>
```
```htmlembedded=
<!DOCTYPE html>
<html lang="zh">
<head>
	<meta charset="UTF-8">
	<title>範例</title>
<style>
	a {
	  text-decoration: none;
	  font-size: 13pt;
	}
	a:link { /*尚未點擊的超連結元素*/
	  color: blue;  
	}
	a:visited { /*已點擊的超連結元素*/
	  color: Crimson;
	}
	a:hover { /*滑鼠滑過的元素*/
	  border: 1px solid black;
	}
	a:active { /*被點選的元素*/
	  color: yellow;
	}
</style>
</head>
<body>
	<h2>網路食譜網站</h2>
	<ul>
	  <li><a href="http://icook.tw/">iCook愛料理</a></li>
	  <li><a href="http://food.tank.tw/">食譜大全</a></li>
	  <li><a href="http://cookpad.com/tw">Cookpad台灣</a></li>
	  <li><a href="http://recipe.piliapp.com">食譜幫</a></li>
	</ul>
</body>
</html>
```
```htmlembedded=
<!DOCTYPE html>
<html>

<head>
    <title>陰影範例</title>    
    <style>
    div{
    	width: 400px;
    	padding: 50px; margin: 10px auto 40px;
        font-size: 15pt; text-align: center;
        color: white; background-color: skyblue;        
    }
    .box1 {
        box-shadow: 10px 10px 5px 5px gray; /*區塊陰影*/
    }
    .box2 {
        box-shadow: 20px 20px 10px 10px gray; 
    }
    </style>    
</head>

<body>
    <div class="box1">Box Shadow</div>
    <div class="box2">Box Shadow</div>
</body>

</html>
```
```htmlembedded=
<!-- 用媒體查詢設計RWD版面
    @media screen and (特性){樣式設定}
-->
<!DOCTYPE html>
<html>

<head>
    <title>媒體查詢範例</title>    
    <style>
    @media screen and (min-width: 320px){
        #container{
           width: 800px; height: 300px;
           padding: 0px;
           margin: 10px auto; 
        }        
        #header{
            height: 50px;
            color: white;
            background-color: darkgray;
            font-size: 24px; text-align: center;
            line-height: 50px;
        }
        #main {
            width:60%; height: 100%;
            color: white;
            background-color: lightgray;
            font-size: 24px; text-align: center;
            line-height: 300px;
            float: left;
        }
        #sidebar{
            width:40%; height: 100%;
            color: gray;
            background-color: whitesmoke;
            font-size: 24px; text-align: center;
            line-height: 300px;
            float: left;
        }
        #footer{
            height: 50px;            
            color: white;
            background-color: darkgray;
            font-size: 24px; text-align: center;
            line-height: 50px;        
            clear: both;
        }        
    }
    @media screen and (max-width: 319px){
        #container{
           width: 300px;
           padding: 0px;
           margin: 10px auto; 
        }        
        #header{
            height: 50px;
            color: white;
            background-color: darkgray;
            font-size: 24px; text-align: center;
            line-height: 50px;
        }
        #main {
            height: 150px;
            color: white;
            background-color: lightgray;
            font-size: 24px; text-align: center;
            line-height: 150px;
        }
        #sidebar{
            height: 150px;
            color: gray;
            background-color: whitesmoke;
            font-size: 24px; text-align: center;
            line-height: 150px;
        }
        #footer{
            height: 50px;
            color: white;
            background-color: darkgray;
            font-size: 24px; text-align: center;
            line-height: 50px;
        }        
    }    
    </style>
</head>

<body>
<div id="container">
    <div id="header">Header</div>
    <div id="main">Content</div>
    <div id="sidebar">Sidebar</div>
    <div id="footer">Footer</div>
</div>
</body>

</html>
```
```htmlembedded=
<!DOCTYPE html>
<html>

<head> <!-- 如想改變變形基準點 可用: transfrom-orgin: 水平位置 垂直位置-->
    <title>變形範例</title>    
    <style>
	div{
	  float:left;
	  width: 100px;
	  height: 100px;
	  margin: 45px;
	  font: bold 50px/100px arial;
	  text-align: center;
	  background-color: lightblue;
	  border: 1px solid black;  
	}
	.box1 {/* 移動*/
	  transform: translate(20px, 10px);
	}
	.box2 {/* 縮放*/
	  transform: rotate(45deg);
	}
	.box3{/* 旋轉*/
	  transform: scale(1.5, 0.5);
	}
	.box4{ /* 傾斜*/
	  transform: skew(20deg, 30deg);
	}
    </style>    
</head>

<body>
	<div class="box1">1</div>
	<div class="box2">2</div>
	<div class="box3">3</div>
	<div class="box4">4</div>
</body>

</html>
<!-- 結果-->
![](https://i.imgur.com/7NzNmql.jpg)

```

