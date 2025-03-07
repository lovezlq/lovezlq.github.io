<script>
// 判断微信内置浏览器环境‌:ml-citation{ref="1,4" data="citationList"}
function isMQQBrowser() {
    const ua = navigator.userAgent.toLowerCase();
    return ua.indexOf('micromessenger') !== -1;
}

// 跳转逻辑控制
if (isMQQBrowser()) {
    // 生成带原始URL参数的跳转中间页‌:ml-citation{ref="2,5" data="citationList"}
    const targetUrl = encodeURIComponent(window.location.href);
    const jumpUrl = `https://www.qq.com`;
    
    // 显示遮罩层引导用户操作‌:ml-citation{ref="4" data="citationList"}
    const mask = document.createElement('div');
    mask.style = 'position:fixed;top:0;left:0;right:0;bottom:0;background:rgba(0,0,0,0.8);z-index:9999;';
    mask.innerHTML = `
        <div style="position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);text-align:center;color:#fff;">
            <h3>请点击右上角菜单</h3>
            <p>选择「在浏览器打开」即可正常访问</p>
            <button onclick="location.href='${jumpUrl}'" 
                style="padding:10px 20px;background:#07c160;border:none;color:#fff;border-radius:5px;margin-top:15px;">
                一键跳转QQ浏览器
            </button>
        </div>
    `;
    document.body.appendChild(mask);
}
</script>
