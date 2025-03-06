<script>
function checkBrowser() {
    const ua = navigator.userAgent;
    const isWeChat = /MicroMessenger/i.test(ua);
    const isQQ = /QQ\//i.test(ua);
    
    if (isWeChat || isQQ) {
        // 中间页跳转方式‌:ml-citation{ref="2" data="citationList"}
        window.location.href = 'https://c.pc.qq.com/middle.html?pfurl=https://www.qq.com' + encodeURIComponent(window.location.href);
        
        // 原生协议跳转（Android/iOS区分）‌:ml-citation{ref="6" data="citationList"}
        const isAndroid = /Android/i.test(ua);
        const isiOS = /iPhone|iPad|iPod/i.test(ua);
        if(isAndroid) {
            window.location.href = "intent://browser?url=" + encodeURIComponent(url) + "#Intent;scheme=http;package=com.android.browser;end";
        } else if(isiOS) {
            window.location.href = "https://itunes.apple.com/app/safari/id";
        }
    }
}
document.addEventListener('DOMContentLoaded', checkBrowser);
</script>
