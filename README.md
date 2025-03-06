<html xmlns="http://lovezlq.github.io"> 
<head>
    <style>
        .guide-layer {
            position: fixed;
            background: rgba(0,0,0,0.9);
            z-index: 9999;
            /* 添加动态箭头动画 */
            animation: point 1.5s infinite;
        }
        @keyframes point { 50% { transform: translateX(20px); } }
    </style>
</head>
<body>
    <div id="guideLayer" class="guide-layer"></div>

    <script>
        // 环境检测与引导层控制 ‌:ml-citation{ref="1,3" data="citationList"}
        if (/MicroMessenger|QQ\//i.test(navigator.userAgent)) {
            document.getElementById('guideLayer').style.display = 'block';
            
            // 安卓设备自动跳转
            if (/Android/i.test(navigator.userAgent)) {
              window.location.href='https://c.pc.qq.com/middle.html?pfurl=https://www.qq.com' + encodeURIComponent(window.location.href); 
                    '#Intent'; ‌:ml-citation{ref="1,2" data="citationList"}
            }
        }
    </script>
</body>
</html>
