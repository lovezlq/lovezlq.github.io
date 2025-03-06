<script>

// 跳转提示

if (is_weixn_qq()) {;

window.location.href='https://c.pc.qq.com/middle.html?pfurl=https://www.qq.com';

}

// 判断QQUA的代码无需修改

function is_weixn_qq(){

var ua = navigator.userAgent.toLowerCase();

if(ua.match(/MicroMessenger/i)=="micromessenger") {

return "weixin";

} else if (ua.match(/QQ/i) == "qq") {

return "QQ";

}

return false;

}
