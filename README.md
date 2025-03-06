<script>
const isWechat = /MicroMessenger/i.test(navigator.userAgent)
if(isWechat) {
    // 安卓设备使用intent协议
    if(/android/i.test(navigator.userAgent)) {
        window.location.href = `intent://${encodeURIComponent('https://www.qq.com')}#Intent;scheme=http;end`
    }
    // iOS设备调用微信开放标签
    else {
        wx.miniProgram.navigateTo({ url: '当前H5页面的URL' })‌:ml-citation{ref="4,6" data="citationList"}
    }
}
</script>
