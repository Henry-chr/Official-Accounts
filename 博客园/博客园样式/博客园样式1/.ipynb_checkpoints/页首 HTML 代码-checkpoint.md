<script src="http://static.tctip.com/tctip-1.0.0.min.js"></script>
  <script>  
  new tctip({
    top: '20%',
    button: {
      id: 9,
      type: 'dashang',
    },
    list: [
      {
        type: 'alipay',
        qrImg: 'https://files.cnblogs.com/files/clwydjgs/zhifubao.bmp'
      }, {
        type: 'wechat',
        qrImg: 'https://files.cnblogs.com/files/clwydjgs/weixin.bmp'
      }
    ]
  }).init()
  </script>

<link  type="text/css" rel="stylesheet" href="https://files.cnblogs.com/files/hafiz/feedback.css">

<script type="text/javascript">
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

1 <link href="http://files.cnblogs.com/files/clwydjgs/cnblog-scroller.css" type="text/css" rel="stylesheet">
2 <script src="http://files.cnblogs.com/files/clwydjgs/scrollspy.js" type="text/javascript"></script>
3 <script src="http://files.cnblogs.com/files/clwydjgs/stickUp.min.js" type="text/javascript"></script>
4 <script src="http://files.cnblogs.com/files/clwydjgs/cnblog-scroller.js" type="text/javascript"></script>