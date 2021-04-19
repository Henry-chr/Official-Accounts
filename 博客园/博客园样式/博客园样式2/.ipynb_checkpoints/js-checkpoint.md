<div id="newsSideBar">
    <div class="headImage">
        <img src="https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1467581611,1841566090&fm=15&gp=0.jpg" alt="头像">
    </div>
</div>



<script type="text/javascript">
/*标签云的动态效果*/
function gotoTop(){
            setTimeout(function(){

                    document.documentElement.scrollTop = (document.documentElement.scrollTop*0.1);
                    document.body.scrollTop = (document.body.scrollTop - document.body.scrollTop*0.1);
                    var scrollTop = document.documentElement.scrollTop || document.body.scrollTop;

                if(scrollTop > 0){
                    gotoTop();
                }
            },10);
        }



var Ftimer = setInterval (Ftoggle,1000),
      contral = [false,false];

function Ftoggle(){
    var tagObjbox = document.getElementsByClassName('catListTag')[0],
              tagObj = tagObjbox.getElementsByTagName('li'),
              navList = document.getElementById('navList');

    if(tagObjbox && tagObj){
       contral[1]=true;
        SlideTag(tagObj);
    }
    if(navList){
       contral[2]=true;
       AddLi(navList);
    }

    if(contral[1] & contral[2]){
       clearInterval(Ftimer);
    }
}

function AddLi(e){
    var li = document.createElement('li'),
        a = document.createElement('a');

    a.innerHTML = '⚪';
    a.className = 'menu';
    a.href = 'https://home.cnblogs.com/u/cainiao-chuanqi/';
    li.appendChild(a);
    e.appendChild(li);


}

function SlideTag(tagObj){

            offset = true;

        PreSeting();

    for(var i=0;i<tagObj.length;i++){
        (function(i){
            tagObj[i].onmouseover = function(){
            offset = false;
            index = parseInt(this.style.zIndex);
            this.style.zIndex = 9999;
            }
            tagObj[i].onmouseout = function(){
            offset = true;
            this.style.zIndex = index;
            }
        })(i);
    }

    setInterval(PreSeting,5000)

    function F_getSJS(x,y,z){

        var int = null;

        if(!z) { z = 6}

        while(int >= x || int <= y || int === null){
            int = Math.random();
            int = (int.toFixed(z) * x).toFixed(0);
        }
        return int;
    }

    function PreSeting(){
             if(offset){
        for(var i=0;i<tagObj.length;i++){
            tagObj[i].style.left = F_getSJS(100,30,10)  + 'px';
            tagObj[i].style.top = F_getSJS(200,30,10) + 'px';
            tagObj[i].style.backgroundColor = 'rgb(' + F_getSJS(256,-1,5) + ',' + F_getSJS(256,-1,10) + ',' + F_getSJS(256,-1,15) + ')';
            tagObj[i].style.zIndex = F_getSJS(200,0,16);
        }
}

    }


}

onload = function(){

if(location.href == 'https://www.cnblogs.com/cainiao-chuanqi/' || location.href == 'https://www.cnblogs.com/cainiao-chuanqi/'){setTimeout(goto,3000);}

function goto(){
         document.getElementById('headbox').style.display = 'block';
         document.documentElement.scrollTop = document.documentElement.scrollTop + 200;
         document.body.scrollTop = document.body.scrollTop + 200;
}
}

</script>



<script type="text/javascript">

/*设置目录（侧边HTML代码）*/
      //以下是锚点JS
      var a = $(document);
      a.ready(function() {
        var b = $('body'),
          d = 'sideToolbar',
          e = 'sideCatalog',
          f = 'sideCatalog-catalog',
          g = 'sideCatalogBtn',
          h = 'sideToolbar-up',
          i = '<div id="sideToolbar"style="display:none;">\<div class="sideCatalogBg"id="sideCatalog">\<div id="sideCatalog-sidebar">\<div class="sideCatalog-sidebar-top"></div>\<div class="sideCatalog-sidebar-bottom"></div>\</div>\<div id="sideCatalog-catalog">\<ul class="nav"style="width:225px;zoom:1">\</ul>\</div>\</div>\<a href="javascript:void(0);"id="sideCatalogBtn"class="sideCatalogBtnDisable"></a>\</div>',
          j = '',
          k = 200,
          l = 0,
          m = 0,
          n = 0,
          //限制存在个数，如数量过多，则只显示h2，不显示h3
          //o, p = 13,
          o, p = 100,
          q = true,
          r = true,
          s = b;
        if(s.length === 0) {
          return
        };
        b.append(i);
        //指定获取目录的范围-------------这一点非常重要，因为每个人指定的范围都不一样，所以这是要修改的地方
        //o = s.find(':header');
        o = $('#cnblogs_post_body').find(':header')
        if(o.length > p) {
          r = false;
          var t = s.find('h2');
          var u = s.find('h3');
          if(t.length + u.length > p) {
            q = false
          }
        };
        o.each(function(t) {
          var u = $(this),
            v = u[0];

          var title = u.text();
          var text = u.text();

          u.attr('id', 'autoid-' + l + '-' + m + '-' + n)
          //if (!u.attr('id')) {
          //    u.attr('id', 'autoid-' + l + '-' + m + '-' + n)
          //};
          if(v.localName === 'h2') {
            l++;
            m = 0;
            if(text.length > 14) text = text.substr(0, 20) + "...";
            j += '<li><span>' + l + '&nbsp&nbsp</span><a href="#' + u.attr('id') + '" title="' + title + '">' + text + '</a><span class="sideCatalog-dot"></span></li>';
          } else if(v.localName === 'h3') {
            m++;
            n = 0;
            if(q) {
              if(text.length > 12) text = text.substr(0, 16) + "...";
              j += '<li class="h2Offset"><span>' + l + '.' + m + '&nbsp&nbsp</span><a href="#' + u.attr('id') + '" title="' + title + '">' + text + '</a></li>';
            }
          } else if(v.localName === 'h4') {
            n++;
            if(r) {
              j += '<li class="h3Offset"><span>' + l + '.' + m + '.' + n + '&nbsp&nbsp</span><a href="#' + u.attr('id') + '" title="' + title + '">' + u.text() + '</a></li>';
            }
          }
        });
        $('#' + f + '>ul').html(j);
        b.data('spy', 'scroll');
        b.data('target', '.sideCatalogBg');
        $('body').scrollspy({
          target: '.sideCatalogBg'
        });
        $sideCatelog = $('#' + e);
        $('#' + g).on('click', function() {
          if($(this).hasClass('sideCatalogBtnDisable')) {
            $sideCatelog.css('visibility', 'hidden')
          } else {
            $sideCatelog.css('visibility', 'visible')
          };
          $(this).toggleClass('sideCatalogBtnDisable')
        });
        $('#' + h).on('click', function() {
          $("html,body").animate({
            scrollTop: 0
          }, 500)
        });
        $sideToolbar = $('#' + d);

        //通过判断评论框是否存在显示索引目录
        var commentDiv = $("#blog-comments-placeholder");

        a.on('scroll', function() {
          //评论框存在才调用方法
          if(commentDiv.length > 0) {
            var t = a.scrollTop();
            if(t > k) {
              $sideToolbar.css('display', 'block');
              $('#gotop').show()
            } else {
              $sideToolbar.css('display', 'none')
              $('#gotop').hide()
            }
          }
        })
      });
      //以上是锚点JS
      //以下是返回顶部JS
      $(function() {
        $('body').append('<div id="gotop" onclick="goTop();"></div>');
      });

      function goTop(u, t, r) {
        var scrollActivate = !0;
        if(scrollActivate) {
          u = u || 0.1;
          t = t || 16;
          var s = 0,
            q = 0,
            o = 0,
            p = 0,
            n = 0,
            j = 0;
          document.documentElement && (s = document.documentElement.scrollLeft || 0, q = document.documentElement.scrollTop || 0);
          document.body && (o = document.body.scrollLeft || 0, p = document.body.scrollTop || 0);
          n = window.scrollX || 0;
          j = window.scrollY || 0;
          s = Math.max(s, Math.max(o, n));
          q = Math.max(q, Math.max(p, j));
          p = 1 + u;
          window.scrollTo(Math.floor(s / p), Math.floor(q / p));
          0 < s || 0 < q ? window.setTimeout('goTop(' + u + ', ' + t + ')', t) : 'undefined' != typeof r && r()
        } else {
          scrollActivate = !0
        }
      }
      //以上是返回顶部JS
    </script>



<div style = "display:none;">动态线条</div>
<script>

!function(){

function n(n,e,t){

return n.getAttribute(e)||t

}

function e(n){

return document.getElementsByTagName(n)

}

function t(){

var t=e("script"),o=t.length,i=t[o-1];

return{

l:o,z:n(i,"zIndex",-1),o:n(i,"opacity",.97),c:n(i,"color","220,20,60"),n:n(i,"count",37)

}

}

function o(){

a=m.width=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,

c=m.height=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight

}

function i(){

r.clearRect(0,0,a,c);

var n,e,t,o,m,l;

s.forEach(function(i,x){

for(i.x+=i.xa,i.y+=i.ya,i.xa*=i.x>a||i.x<0?-1:1,i.ya*=i.y>c||i.y<0?-1:1,r.fillRect(i.x-.5,i.y-.5,1,1),e=x+1;e<u.length;e++)n=u[e],

null!==n.x&&null!==n.y&&(o=i.x-n.x,m=i.y-n.y,

l=o*o+m*m,l<n.max&&(n===y&&l>=n.max/2&&(i.x-=.03*o,i.y-=.03*m),

t=(n.max-l)/n.max,r.beginPath(),r.lineWidth=t/2,r.strokeStyle="rgba("+d.c+","+(t+.2)+")",r.moveTo(i.x,i.y),r.lineTo(n.x,n.y),r.stroke()))

}),

x(i)

}

var a,c,u,m=document.createElement("canvas"),

d=t(),l="c_n"+d.l,r=m.getContext("2d"),

x=window.requestAnimationFrame||window.webkitRequestAnimationFrame||window.mozRequestAnimationFrame||window.oRequestAnimationFrame||window.msRequestAnimationFrame||

function(n){

window.setTimeout(n,1e3/45)

},

w=Math.random,y={x:null,y:null,max:2e4};m.id=l,m.style.cssText="position:fixed;top:0;left:0;z-index:"+d.z+";opacity:"+d.o,e("body")[0].appendChild(m),o(),window.onresize=o,

window.onmousemove=function(n){

n=n||window.event,y.x=n.clientX,y.y=n.clientY

},

window.onmouseout=function(){

y.x=null,y.y=null

};

for(var s=[],f=0;d.n>f;f++){

var h=w()*a,g=w()*c,v=2*w()-1,p=2*w()-1;s.push({x:h,y:g,xa:v,ya:p,max:6e3})

}

u=s.concat([y]),

setTimeout(function(){i()},100)

}();

</script>
<div style = "display:none;"> 动态线条end</div>



