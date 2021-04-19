<!--  页首代码 星光-->

<div id="midground" class="wall"></div>
<div id="foreground" class="wall"></div>
<div id="top" class="wall"></div>


<!--  设置目录（首页HTML代码）-->
<link  type="text/css" rel="stylesheet" href="https://files.cnblogs.com/files/miangao/maodian.css">



<!--  页面HTML/JS部分 页面展开动画-->
<div id="fry_append">

<div id="fry_sidebar">侧边栏</div>

</div>
<!-- 页面展开动画-->
<script type="text/javascript">
function my_unfold(){
    width_main=$('#main').width();
    height_main=$('#main').height();
    time=1000;
    function unfoldLeft(width,height,time) {
        $('#main').animate({
            'width': '0%',
            'height': '0%',
            opacity: '0'
        }, 0,'linear');
        $('#main').animate({
            'width': '+'+width_main,
            'height': '+'+height_main,
            opacity: '1'
        }, time,'linear');
    }
    unfoldLeft(width_main,height_main,time);
}
</script>

<!--END 页面展开动画-->
<!-- 展开侧边栏 -->
<script type="text/javascript">
$('#main').append('<div id="fry_append"><hr/><div id="fry_sidebar">侧边栏</div></div>');
$('#fry_sidebar').click(function(){
    $('#mainContent .forFlow').css({'margin-right':'0px'});
    if($('#sideBar').css('display')=='none'){
        var width=$(window).width()*0.93;
        var width1=$(window).width()*0.97-300;
        var width2=($(window).width()-280)/2;
        if(width*0.35<230){
                $('#mainContent').css({'display':'none'});
                $('#sideBar').css({'display':'block','width':'280','margin-right':width2+'px'});
        }else{
                $('#sideBar').css({'display':'block','width':'277px','margin':'none','float':'right'});
                $('#mainContent').css({'display':'block','width':width1+'px'});
        }
    }
    else{
        $('#sideBar').css({'display':'none'});
        $('#mainContent').css({'display':'block','width':'123%'});
    }
});

</script>



<script src="https://files.cnblogs.com/files/cainiao-chuanqi/mouse-click.js"></script>
<canvas width="1777" height="841" style="position: fixed; left: 0px; top: 0px; z-index: 2147483647; pointer-events: none;"></canvas>



<script type="text/javascript">
/*设置小心心*/
(function(window, document, undefined) {
    var hearts = [];
    window.requestAnimationFrame = (function() {
        return window.requestAnimationFrame || window.webkitRequestAnimationFrame || window.mozRequestAnimationFrame || window.oRequestAnimationFrame || window.msRequestAnimationFrame ||
        function(callback) {
            setTimeout(callback, 1000 / 60);
        }
    })();
    init();
    function init() {
        css(".heart{width: 10px;height: 10px;position: fixed;background: #f00;transform: rotate(45deg);-webkit-transform: rotate(45deg);-moz-transform: rotate(45deg);}.heart:after,.heart:before{content: '';width: inherit;height: inherit;background: inherit;border-radius: 50%;-webkit-border-radius: 50%;-moz-border-radius: 50%;position: absolute;}.heart:after{top: -5px;}.heart:before{left: -5px;}");
        attachEvent();
        gameloop();
    }
    function gameloop() {
        for (var i = 0; i < hearts.length; i++) {
            if (hearts[i].alpha <= 0) {
                document.body.removeChild(hearts[i].el);
                hearts.splice(i, 1);
                continue;
            }
            hearts[i].y--;
            hearts[i].scale += 0.004;
            hearts[i].alpha -= 0.013;
            hearts[i].el.style.cssText = "left:" + hearts[i].x + "px;top:" + hearts[i].y + "px;opacity:" + hearts[i].alpha + ";transform:scale(" + hearts[i].scale + "," + hearts[i].scale + ") rotate(45deg);background:" + hearts[i].color;
        }
        requestAnimationFrame(gameloop);
    }
    function attachEvent() {
        var old = typeof window.onclick === "function" && window.onclick;
        window.onclick = function(event) {
            old && old();
            createHeart(event);
        }
    }
    function createHeart(event) {
        var d = document.createElement("div");
        d.className = "heart";
        hearts.push({
            el: d,
            x: event.clientX - 5,
            y: event.clientY - 5,
            scale: 1,
            alpha: 1,
            color: randomColor()
        });
        document.body.appendChild(d);
    }
    function css(css) {
        var style = document.createElement("style");
        style.type = "text/css";
        try {
            style.appendChild(document.createTextNode(css));
        } catch(ex) {
            style.styleSheet.cssText = css;
        }
        document.getElementsByTagName('head')[0].appendChild(style);
    }
    function randomColor() {
        return "rgb(" + (~~ (Math.random() * 255)) + "," + (~~ (Math.random() * 255)) + "," + (~~ (Math.random() * 255)) + ")";
    }
})(window, document);
</script>



<script type="text/javascript"> 
/*自定义的鼠标点击效果*/
/* 鼠标特效 */ 
var a_idx = 0; 
jQuery(document).ready(function($) { 
    $("body").click(function(e) { 
        var a = new Array("富强","民主","文明","和谐","菜鸟-传奇","自由","平等","公正","法治","菜鸟-传奇","爱国","敬业","诚信","友善","菜鸟-传奇"); 
        var $i = $("<span/>").text(a[a_idx]); 
        a_idx = (a_idx + 1) % a.length; 
        var x = e.pageX, 
        y = e.pageY; 
        $i.css({ 
            "z-index": 999999999999999999999999999999999999999999999999999999999999999999999, 
            "top": y - 20, 
            "left": x, 
            "position": "absolute", 
            "font-weight": "bold", 
            "color": "rgb(119,136,153)" 
        }); 
        $("body").append($i); 
        $i.animate({ 
            "top": y - 180, 
            "opacity": 0 
        }, 
        1500, 
        function() { 
            $i.remove(); 
        }); 
    }); 
}); 
</script>



<!-- 此处放入页首Begin -->
    <div id="loadingbar">
        <div id="loadingProcess"></div>
    </div>
    <script type="text/javascript">
        var loadingProcess = 0;
        var isLoading = true;
        var $loadingProcess = $('#loadingProcess');
        function loading() {
            loadingProcess += 1;
            if (loadingProcess >= 80) {
                loadingProcess = 80;
            }
            $loadingProcess.css('width', loadingProcess + '%');
            if (!isLoading && loadingProcess === 80) {
                $loadingProcess.css('width', '100%').hide(200);
            } else {
                requestAnimationFrame(loading);
            }
        }
        loading();
        $(function () {
            isLoading = false;
        })
    </script>
    <!-- 此处放入页首End -->
   <!-- 此处放入页首Begin -->
   <div id="loadingProcess"></div>
   <script type="text/javascript">
       var loadingProcess = 0;
       var isLoading = true;
       var $loadingProcess = $('#loadingProcess');
       function loading() {
           loadingProcess += 1;
           if (loadingProcess >= 80) {
               loadingProcess = 80;
           }
           $loadingProcess.css('width', loadingProcess + '%');
           if (!isLoading && loadingProcess === 80) {
               $loadingProcess.css('width', '100%').hide(200);
           } else {
               requestAnimationFrame(loading);
           }
       }
       loading();
       $(function () {
           // 页面加载完毕，停掉加载动画
           isLoading = false;
           // 载入小磁怪
           if ($('#div_digg').length === 1 || window.location.href.indexOf('\/p\/')!==-1) {
               $(document.body).append('<img id="xiaociguai" title="电磁波切换" alt="电磁波切换" src="http://images.cnblogs.com/cnblogs_com/vvjiang/996881/o_xiaociguai1.jpg" />')
               // 绑定停止精灵球跳动按钮
               var isStopJump = false;
               $('#xiaociguai').click(function (e) {
                   if (isStopJump) {
                       $('#div_digg').css('animation', 'jumping 5s ease-in-out').css('animation-iteration-count', 'infinite');
                       $('#xiaociguai').removeClass('enable-electric')
                   } else {
                       $('#div_digg').css('animation', 'unset');
                       $('#xiaociguai').addClass('enable-electric')
                   }
                   isStopJump = !isStopJump;
               })
           }
       })
   </script>
   <!-- 此处放入页首End -->