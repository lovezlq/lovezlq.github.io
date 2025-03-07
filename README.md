<!-- 跳转失败时显示引导层‌:ml-citation{ref="6,7" data="citationList"} -->
<div id="qq-mask" style="display:none;position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,0.9);z-index:9999;">
    <div style="position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);color:#fff;text-align:center;">
        <h3>当前页面需通过外部浏览器访问</h3>
        <button onclick="handleExternalJump()" 
            style="padding:12px 24px;background:#31A8E6;color:#fff;border:none;border-radius:8px;margin-top:20px;">
            点击跳转外部浏览器
        </button>
    </div>
</div>

<script>
// 环境检测与交互逻辑‌:ml-citation{ref="2,3" data="citationList"}
function isQQBrowser() {
    return navigator.userAgent.indexOf('QQ/') > -1;
}

function handleExternalJump() {
    const targetUrl = encodeURIComponent(window.location.href);
    // 调用通用跳转协议‌:ml-citation{ref="5" data="citationList"}
    window.open(`mqqbrowser://open?url=${targetUrl}`, '_system');
}

// 3秒后检测是否仍在QQ环境‌:ml-citation{ref="3,7" data="citationList"}
setTimeout(() => {
    if (isQQBrowser()) {
        document.getElementById('qq-mask').style.display = 'block';
    }
}, 3000);
</script>
