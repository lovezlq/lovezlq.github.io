<html>
// 点击按钮触发跳转检测 ‌:ml-citation{ref="5,7" data="citationList"}
document.getElementById('downloadBtn').addEventListener('click', () => {
    if (isWeixin || isQQ) {
        showBrowserGuide(); // 显示引导层
    } else {
        directDownload(); // 直接执行操作
    }
});
</head>
