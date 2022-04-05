2021-12-27~2022-04-01
===
###### tags: `JS紀錄區`
```javascript=
window.alert();/*彈出方塊*/
window.prompt();/*對話方塊*/
document.write();/*將內容寫在網頁上*/
document.getElementById()/*取得ID元素*/
parseInt(); /*將字串轉為整數(不含小數)*/
parseFloat(); /*將字串轉為整數(含小數)*/
```
```javascript=
/*簡易對話*/
let my_name = prompt('請輸入你的名字');
let my_age = prompt('請輸入你的年紀');
document.write('你好阿' + my_name);
document.write('你今年' + my_age + '歲');

/*簡易計算機*/
let num1 = prompt('請輸入數字1');
let num2 = prompt('請輸入數字2');
num1 = parseInt(num1); /*將字串轉為整數(不含小數)*/
num2 = parseInt(num2);
document.write(num1 + num2);

/* if判斷 &&且 ||或 */
var score = 50;
if(score == 100){
    document.write("我給你1000元");
}
else if(score >=60){
    document.write("我給你500元");
}
else{
    document.write("你好爛");
}

/*for迴圈*/
let animate = ["SAO", "RE0", "MLTD"];
for(let i = 0; i<animate.length; i++){
    document.write(animate[i]);
    document.write('<br>');
}

/*簡易問答程式*/
let questions = [
            {
                prompt:"1+1等於多少? (a)1 (b)2 (c)3",
                answer:"b"
            },
            {
                prompt:"10+1等於多少? (a)11 (b)12 (c)13",
                answer:"a"
            },
            {
                prompt:"1+11等於多少? (a)11 (b)12 (c)13",
                answer:"b"
            }
        ];
let score = 0;
for(let i = 0; i<questions.length; i++){
    let input = prompt(questions[i].prompt);
    if(input == questions[i].answer){
        score++;
        alert("恭喜答對");
    }
    else{
        alert("答錯了");
    }
}

alert("總共答對" + score +"題");

```
```htmlembedded=
<!DOCTYPE html>
<!-- 製作線上計時器-->
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div id="clock"></div>
    <button type="button" id="btn">停止線上時鐘</button>


    <script>
        window.addEventListener('load', function(){
            var timer = window.setInterval(function(){
                /*每隔一秒更新一次時間*/
                var clock = document.getElementById('clock');
                clock.textContent = (new Date()).toLocaleString();
            }, 1000);

            var btn = document.getElementById('btn');
        btn.addEventListener('click', function(){
            /*按下停止，會清除計時器*/
            window.clearInterval(timer);
        }, false);
        }, false);

```

```javascript=
function check() {/*提交表單*/
    var id = document.getElementById("id");
    var pass = document.getElementById("email");
    alert("回覆成功!謝謝您的回覆，預計於36525個工作天內回覆，請耐心等待");
}

let img = document.getElementById("img");
        img.addEventListener("mouseover",function(){/*滑鼠移入*/
    this.src = ""/*放入圖片*/;
});

            img.addEventListener("mouseout",function(){/*滑鼠移出*/
    this.src = ""/*放入圖片*/;
});
```
```javascript=
/*音樂自動撥放*/
window.onload = function(){
    setInterval("toggleSound()",100);
}

function toggleSound() {
       var music = document.getElementById("aud");//獲取ID

       if (music.paused) { //判讀是否播放
           music.paused=false;
           music.play(); //沒有就播放
       }
}
```
2022-04-04
===
```javascript=
/*JQuery語法*/
$(選擇器).method(參數);

.each() /*用來針對物件或陣列進行重複運算*/
 var sum = 0;
 var arr = [1,2,3,4,5];
 $.each(arr, function(index, value){
        sum += value;
 });

 window.alert(sum);

.css()/*存取CSS設定*/
$('h1'),css({
    'color' : 'red',
    'background-color' : 'yellow',
    'text-shadow' : 'gray 3px 3px'
    
});

/*繫結<h1>元素的mouseover事件與處理程式*/
        $('h1').on('mouseover', function(){
            $(this).css({
        'color' : 'red',
        'text-shadow' : 'gray 3px 3px'
        });

/*繫結<h1>元素的mouseout事件與處理程式*/
        $('h1').on('mouseout', function(){
            $(this).css({
        'color' : 'black',
        'text-shadow' : 'none'
        });
```
```javascript=
.on(); /*事件處理*/
.on(events[, selector] [, data], handler);
/*events ->事件名稱 ex:'click'或'click dbclick'
  selector ->設定觸發事件的元素
  data ->設定要傳遞給處理程式的資料
  handler ->設定當事件被觸發時所要執行的函式，即處理程式
 */
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://code.jquery.com/jquery-3.6.0.min.js" integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4=" crossorigin="anonymous"></script>
    <title>Document</title>
</head>
<body>
    <input type="text">
    <p></p>


    <script>
        $('input').on('click', function(){
            $('p').text('被點了一下');
        });
    </script>
</body>
</html>
```
```javascript=
/*基本特效 .hide() .show() ,toggle()->循環切換*/
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://code.jquery.com/jquery-3.6.0.min.js" integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4=" crossorigin="anonymous"></script>
    <title>Document</title>
</head>
<body>
    <button id="btn1">隱藏</button>
    <button id="btn2">顯示</button>
    <p>你好</p>


    <script>
        /*點擊隱藏鈕，p段落文字被隱藏600秒*/
        $('#btn1').on('click' , function(){
            $('p').hide(600);
        });

        /*點擊顯示鈕，p段落文字被顯示600秒*/
        $('#btn2').on('click' , function(){
            $('p').show(600);
        });
    </script>


</body>
</html>

/* .fadeIn() ->淡入、
   .fadeOut() ->淡出
   .slideDown() ->、移入、
   .slideUp() ->移出特效
   .fadeTo(400 ,0.5) ->透明度, 0.0~1.0
   .fadeToggle() ->循環切換淡入、淡出
   .slideToggle() ->循環切換移入、移出
 */
/*點擊隱藏鈕，p段落文字以淡出特效被隱藏600秒*/
        $('#btn1').on('click' , function(){
            $('p').fadeOut(600);
        });

        /*點擊顯示鈕，p段落文字以淡入特效被顯示600秒*/
        $('#btn2').on('click' , function(){
            $('p').fadeIn(600);
        });

/*自訂動畫 .animate()*/
$(#enlarge).on('click', function(){
    $('img').animate({
        width: '300px',
        opacity: 1,
        borderWidth: '10px'
    }, 1500);
});
```


