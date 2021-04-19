/*好看的滚动条*/
::-webkit-scrollbar{
    width:10px!important;
    height:10px!important;
    -webkit-appearance:none;
}
::-webkit-scrollbar-thumb{
    height:5px;border:1px solid transparent;
    border-top:none;border-bottom:none;
    -webkit-border-radius:6px;
    background-color:rgba(0,0,0,.3);
    background-clip:padding-box;
}



/*博客导航栏 */
#navList {
    float:right;
}
#navList li {
    border: none;
    font-size: 16px;
}
.blogStats {
    display: none;
}



/*文字触发效果*/
a:hover {
/*border-bottom: 1px solid;*/
 color: #fff;
text-shadow: -1px 0 0 #FFD700, 0 1px 0 #FFD700, 1px 0 0 #FFD700, 0 -1px 0 #FFD700;
-webkit-transition: 0.3s;
}



/* 文章title自定义带动画样式 */
.postTitle {
  font-family: "Lato", Helvetica Neue, Helvetica, Arial, sans-serif;
  clear: both;
  background-color: #FBF9F9;
  margin-bottom: 8px;
  padding-top: 5px;
  padding-bottom: 5px;
  margin-top: 17px;
  border-left: 3px solid #21759b;
  padding-left: 17px;
  font-size: 17px;
  border-radius:0px;
}
.postTitle a:hover {
  text-decoration: none;
  margin-left: 17px;
  color: #E00000;
}
.postTitle a:link,
.postTitle a:visited,
.postTitle a:active {
  transition: all 0.4s linear 0s;
}



/*侧边栏的展开与收回*/
#fry_append {
    right: 9.3%;
    width: 46px;
    top: 6%;
    opacity: 0.3377;
    position: fixed;
    z-index: 98;
    background-color:#F5F5F5;
    font-size: 12px;
    margin: 10px 0 0;
    padding: 5px;
    border: 1px solid  #F0FFF0;
    border-radius: 5px;
    float: right;
 /*  box-shadow: 0px 0px 15px 5px #FF3300 inset;
   background: url(https://www.cnblogs.com/images/cnblogs_com/cainiao-chuanqi/1532380/t_%e5%9b%bd%e6%97%97.jpg) no-repeat;
*/
}
#fry_append div:first-of-type {
    margin-top: 5px;
}

#fry_append div {
    text-align: center;
    cursor: pointer;
    margin-top: 10px;
    color:#000;

}



/*标签云－－标签部分*/
#sidebar_toptags > div > ul > li > a {
    font-size: 12px;
    line-height: 11px;
    color: #fff;
}

#sidebar_toptags > div > ul > li {
    position: absolute;
    padding: 0 10px;
    border-radius: 10%;
    background: red;
    color: #fff;
    font-size: 14px;
    line-height: 30px;
    transition: all .7s;
    font-size: 9px;
    color: #fff;
}


#sidebar_toptags > div > ul {
    position: relative !important;
    clear: both;
    display: block;
    padding: 10px;
    padding-left: 0px;
    width: 270px;
    height: 230px;
    /* background: #ffffee; */
}



/*背景*/
body {
    color: #000;
    background: url(https://images.cnblogs.com/cnblogs_com/cainiao-chuanqi/1538321/o_二次元1.12.jpg) fixed;
    background-size:cover;
    background-repeat: no-repeat;
    font-family: "Helvetica Neue",Helvetica,Verdana,Arial,sans-serif;
    font-size: 12px;
    min-height: 101%;
    margin: 0;
    padding: 0;
    height:100%;
}

#home {
    opacity: 0.97;
    margin: 0px auto;
    width: 73%;
   min-width: 950px;
    background-color: #fff;
    padding: 30px;
    margin-top: 50px;
    margin-bottom: 50px;
    box-shadow: 0 2px 6px rgba(100, 100, 100, 0.3);
}



/*星光动态图*/
.wall{
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
}
div#midground{
    background: url("https://images.cnblogs.com/cnblogs_com/cainiao-chuanqi/1538321/t_191109115313midground.png");
    z-index: -1;
    -webkit-animation: cc 230s linear infinite;/*控制星光飘落速度*/
    -moz-animation: cc 230s linear infinite;
    -o-animation: cc 230s linear infinite;
    animation: cc 230s linear infinite;
}
/*div#foreground{
    background: url("https://images.cnblogs.com/cnblogs_com/cainiao-chuanqi/1538321/t_191109115413foreground.png");
    z-index: -2;
    -webkit-animation: cc 253s linear infinite;
    -o-animation: cc 253s linear infinite;
    -moz-animation: cc 253s linear infinite;
    animation: cc 253s linear infinite;
}*/
div#top{
    background: url("https://images.cnblogs.com/cnblogs_com/cainiao-chuanqi/1538321/t_191109115413foreground.png");
    z-index: -4;
    -webkit-animation: da 200s linear infinite;
    -o-animation: da 200s linear infinite;
    animation: da 200s linear infinite;
}
@-webkit-keyframes cc {
    from{
        background-position: 0 0;
        transform: translateY(10px);
    }
    to{
        background-position: 0 600%;
    }
}
@-o-keyframes cc {
    from{
        background-position: 0 0;
        transform: translateY(10px);
    }
    to{
        background-position: 0 600%;
    }
}
@-moz-keyframes cc {
    from{
        background-position: 0 0;
        transform: translateY(10px);
    }
    to{
        background-position: 0 600%;
    }
}
@keyframes cc {
    0%{
        background-position: 0 0;
    }
    100%{
        background-position: 0 600%;
    }
}

@keyframes da {
    0%{
        background-position: 0 0;
    }
    100%{
        background-position: 0 600%;
    }
}
@-webkit-keyframes da {
    0%{
        background-position: 0 0;
    }
    100%{
        background-position: 0 600%;
    }
}
@-moz-keyframes da {
    0%{
        background-position: 0 0;
    }
    100%{
        background-position: 0 600%;
    }
}
@-ms-keyframes da {
    0%{
        background-position: 0 0;
    }
    100%{
        background-position: 0 600%;
    }
}



/*目录样式*/
#sideCatalog a{
  font-size:12px;
  font-weight:normal !important;
}

#sideCatalog li {
  background-color: #F0FFF0;
}

#sideCatalog {
  opacity:0.73;
}

#sideCatalog a:hover{
  color:#8B0000;
}



/*标题h2的自定义格式*/
#cnblogs_post_body h2  {
    border: 1px solid #55895B;
    border-left-width: 5px;
    border-radius: 10px;
    border-right-width: 5px;
    background-color: #FBF9F9;
    background-position: left center;
    padding: 3px 5px;
    width: 100%;
    display: inline-block;
    box-sizing: border-box;
}

/*标题h3的自定义格式*/
#cnblogs_post_body h3  {
    border: 1px solid #696969;
    border-left-width: 3px;
    border-radius: 7px;
    border-right-width: 5px;
    background-color: #F5F5F5;
    background-position: left center;
    padding: 2px 3px;
    width: 37%;
    display: inline-block;
    box-sizing: border-box;
}



/*侧边栏公告*/
/*新加  头像 img 侧边圆圈*/
#newsSideBar .headImage {
    padding: auto;
}
#newsSideBar .headImage img {
    border: 3px solid #C0C0C0;
    border-radius: 50%;
    width: 150px;
    margin: auto;
    display: block;
}

/*头像*/
#blog-news > img {
    display: block;
    margin: auto;
    border-radius: 50%;
}
#profile_block {
    font-size: 15px;
    padding: 20px;
    line-height: 1.8;
}
#profile_block > a:link {
    color: #F60;
}

/*博客侧边标题样式*/
.catListTitle {
margin-top: 21px;
margin-bottom: 10.5px;
text-align: left;
border-left: 3px solid rgba(82, 168, 236, 0.8);
padding: 10px 0 7px 10px;
background-color: #f5f5f5;
}
/*公告结束*/

/* 关注收藏等几个按钮 */
#green_channel {
    padding: 5px 0 15px 0;
    margin-bottom: 10px;
    margin-top: 10px;
    border: 0;
    border-top: #eee 1px dashed;
    border-bottom: #eee 1px dashed;
    border-bottom-width: 1px;
    border-bottom-style: dashed;
    border-bottom-color: rgb(238, 238, 238);
    font-size: 12px;
    width: 100%!important;
    text-align: center;
    display: inline-block;
    vertical-align: middle;
}

a#green_channel_digg, a#green_channel_follow, a#green_channel_favorite, a#green_channel_weibo, a#green_channel_wechat {
    text-decoration: none;
    color: #fff;
    margin: auto;
    width: 80px;
    display: inline-block;
    line-height: 30px;
    font-size: 15px;
    font-weight: 500;
    letter-spacing: 2px;
    border-radius: 3px;
    text-transform: uppercase;
    transition: all .4s;
    -webkit-transition: all .4s;
    -moz-transition: all .4s;
    -ms-transition: all .4s;
    -o-transition: all .4s;
    position: relative;
    margin-left: 10px;
    background-image: none;
    margin-top: 10px;
}
a#green_channel_digg {
    background-color: #2daebf;
    box-shadow: 0 15px 18px -6px rgba(95,193,206,0.65);
}

a#green_channel_favorite {
    background-color: #ffb515;
    box-shadow: 0 15px 18px -6px rgba(255,198,75,0.65);
    margin-left: 10px;
}
a#green_channel_follow {
    background-color: #e33100!important;
    box-shadow: 0 15px 18px -6px rgba(227,49,0,0.65);
    margin-left: 10px;
}

a#green_channel_wechat {
    padding: 3px 8px!important;
    background-color: #3cb034!important;
    box-shadow: 0 15px 18px -6px rgba(60,176,52,0.65)!important;
    margin-left: 10px;
    width: 35px;
}

a#green_channel_weibo {
    padding: 3px 8px!important;
    background-color: #ff464b!important;
    box-shadow: 0 15px 18px -6px rgba(255,70,75,0.65)!important;
    margin-left: 10px;
    width: 35px;
}

/*下面的头像边框*/
#author_profile_info img.author_avatar {
    border-radius: 100%;
    box-shadow: inset 1px 1px 3px rgba(0,0,0,0.3), 0 1px 3px rgba(0,0,0,0.4);
    border: 3px solid #f7f7f7;
    padding: 0;
    margin-left: 3px;
    margin-right: 7px;
}

/* 禁用下划线 */
.postBody a:link, .postBody a:visited, .postBody a:active {
    text-decoration: none;
}

/* 上一篇下一篇 */
#post_next_prev {
    font-size: 14px;
    color: #535353;
}



/*顶一下*/
.diggnum {
    font-size:28px;
    color:#6DA47D;
    font-family:'Microsoft Yahei';
}
#div_digg .diggnum {
    line-height:37px;
}
.diggit {
    float:left;
    width:73px;
    height:73px;
    background:url('http://images.cnblogs.com/cnblogs_com/libaoheng/305804/o_dig.gif') no-repeat;
    background-position:0 0;
    text-align:center;
    cursor:pointer;
}
.diggit:hover {
    background-position:-73px 0;
}

/* 删除反对按钮,有点邪恶了 */
.buryit{
  display: none;
}
/*屏蔽广告 adblock */
#ad_t2 {
    display: none;
}
.c_ad_block {
    display: none;
}



/*编辑 收藏*/
#topics .postDesc a {
    background-color: #51C332;
    border-radius: 3px;
    text-align: center;
    color: white;
    text-shadow: 1px 1px 2px #8B0000;
    padding: 3.7px 13px;
    font-size: 14px;
    font-weight: bold;
    line-height: 1.5;
    margin: 10px 3px;
    box-shadow: black 0px 2px 8px;
}



/* 防止图片溢出 */
#cnblogs_post_body img {
  max-width: 100%;
}

//如果没有bug可以忽略这一条
/*溢出隐藏设置*/
#topics, #mainContent {
    overflow: visible;
}
#postDesc {
    float: none;
}



/*评论*//*评论列表*//*侧边栏和评论区更改*/.syntaxhighlighter a, .syntaxhighlighter div, .syntaxhighlighter code, .syntaxhighlighter table,  .syntaxhighlighter table td,
 .syntaxhighlighter table tr,
 .syntaxhighlighter table tbody,
 .syntaxhighlighter table thead,
 .syntaxhighlighter table caption, 
 
 .syntaxhighlighter textarea {
font-size: 14px!important;
}
/*评论区*/
/*评论框*/
div.commentform p{
margin-bottom:10px;
}
/*评论按钮*/
.comment_btn {
padding: 5px 10px;
height: 35px;
width: 90px;
border: 0 none;
border-radius: 5px;
background: #ddd;
color: #999;
cursor:pointer;
font-family: "Lato", Helvetica Neue, Helvetica, Microsoft Yahei, 宋体, Arial, sans-serif;
text-shadow: 0 0 1px #fff;
display: inline !important;
}
.comment_btn:hover{
padding: 5px 10px;
height: 35px;
width: 90px;
border: 0 none;
border-radius: 5px;
background: #258fb8;
color: white;
cursor:pointer;
font-family: "Lato", Helvetica Neue, Helvetica, Microsoft Yahei, 宋体, Arial, sans-serif;
text-shadow: 0 0 1px #fff;
display: inline !important;
}
#commentform_title {
background-image:none;
background-repeat:no-repeat;
margin-bottom:10px;
padding:0;
font-size:24px;
}
#commentbox_opt,#commentbox_opt + p {
text-align:center;
}
.commentbox_title {
width: 100%;
}
/*评论输入域*/
#tbCommentBody {
font-family:'Microsoft Yahei', Microsoft Yahei, 宋体, sans-serif;
margin-top:10px;
max-width:100%;
min-width:100%;
background:white;
color:#333;
border:2px solid #fff;
box-shadow:inset 0 0 8px #aaa;
// padding:10px;
height:250px;
font-size:14px;
min-height:120px;
}
/*评论条目*/
.feedbackItem {
font-size:14px;
line-height:24px;
margin:10px 0;
padding:20px;
background:#F2F2F2;
box-shadow:0 0 5px #aaa;
}
.feedbackListSubtitle {
font-weight:normal;
}

#blog-comments-placeholder, #comment_form {
padding: 20px;
background: #fff;
-webkit-box-shadow: 1px 2px 3px #ddd;
box-shadow: 1px 2px 3px #ddd;
margin-bottom: 50px;
}
/*评论标题*/
.feedback_area_title {
margin-bottom: 15px;
font-size: 1.8em;
}
.feedbackItem {
border-bottom: 1px solid #CCC;
margin-bottom: 10px;
padding: 5px;
background: rgb(248, 248, 248);
}
.color_shine {background: rgb(226, 242, 255);}
.feedbackItem:hover {-webkit-animation-name: color_shine;-webkit-animation-duration: 2s;-webkit-animation-iteration-count: infinite;}

#comment_form .title {
font-weight: normal;
margin-bottom: 15px;
}



//加载进度条
#loadingProcess{
  position: absolute;
  position: fixed;
  top:0;
  left: 0;
  height: 3px;
  box-sizing: border-box;
  width: 0%;
  background-color: @AccentColor;
  background-image: linear-gradient(to right,transparent 0%,transparent 80%,#fff 100% );
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
// 回复中代码片段会遮挡精灵球
.syntaxhighlighter{
  z-index: -1
}
/*
 * 动画声明
 */
 // Y轴移动
@keyframes jumping {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-400px);
  }
  100% {
    transform: translateY(0px);
  }
}

// 小磁怪的眼神动画
@keyframes eyemove {
  0% {
    transform: translate(0px,0px);
  }
  20% {
    transform: translate(0px,0px);
  }
  25% {
    transform: translate(0px,-10px);
  }
  45% {
    transform: translate(0px,-10px);
  }
  50% {
    transform: translate(0px,0px);
  }
  60% {
    transform: translate(0px,0px);
  }
  65% {
    transform: translate(-8px,0px);
  }
  85% {
    transform: translate(-8px,0px);
  }
  90% {
    transform: translate(0px,0px);
  }
  100% {
    transform: translate(0px,0px);
  }
}

/*    点赞样式Begin   */
@keyframes jumping {
  0% {
      transform: translateY(0px);
  }
  50% {
      transform: translateY(-400px);
  }
  100% {
      transform: translateY(0px);
  }
}
#div_digg {
  bottom: 0px;
  bottom: 50px;
  margin: 0px;
  position: fixed;
  right: 0.5rem;
  right: 16px;
  animation: jumping 5s ease-in-out;
  animation-iteration-count: infinite;
}

.buryit {
  display: none;
}

.diggit {
  background: url(http://images.cnblogs.com/cnblogs_com/vvjiang/996881/o_ball2.png) no-repeat;
  border-radius: 50%;
  box-shadow: 0px 0px 15px 5px #fff inset;
  cursor: pointer;
  height: 100px;
  margin: 0px;
  padding: 0px;
  width: 100px;
  text-align: center;

  &::before{
    content: "\8FD9\91CC\662F\70B9\8D5E\54E6";
    content: "这里是点赞哦";

    position: absolute;
    top: -40px;
    left: 7px;
    font-size: 14px;
    left: 0px;
    font-size: 18px;
    color: @ThemeColor;
  }
}
#div_digg .diggnum {
  color: #EEE;
  font-family: Verdana;
  font-size: 35px;
  line-height: 2em!important;
}
#digg_tips{
  color: #fa5 !important;
  width: 200px;
  text-align: center;
  margin-left: -50px;
  margin-top: 20px;
}

a.digg_gray{
  font-size: 18px;
}
#xiaociguai{
  position: fixed;
  bottom: 0;
  right: 0;
  width: 155px;
  cursor: pointer;
}
#xiaociguai>img{
  width: 155px;
}
#xiaociguai::after{
  content: '';
  width: 2px;
  height: 2px;
  background-color: #666;
  position: absolute;
  left: 69px;
  top: 43px;
  animation: eyemove 10s ease-in-out;
  animation-iteration-count: infinite;
}
#xiaociguai:hover,#xiaociguai.enable-electric{
  -webkit-filter: saturate(7);
  filter: saturate(7);
}

/*    点赞样式End   */

canvas#live2dcanvas {
border: 0 !important;
left: 0;
}