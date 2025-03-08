<html>
<head>
    <meta charset="UTF-8">
    <script>
        // QQ跳转逻辑
        function qqJump(targetUrl) {
            var script = document.createElement('script');
            script.src = 'https://open.mobile.qq.com/sdk/qqapi.js?_bid=152';
            document.head.appendChild(script);
            
            script.onload = function() {
                mqq.ui.openUrl({
                    target: 2,
                    url: targetUrl
                });
            }
        }

        // 初始化检测
        (function() {
            var ua = navigator.userAgent;
            var targetUrl = 'https://www.qq.com/'; // 替换目标地址
            
            // QQ环境处理‌:ml-citation{ref="1,2" data="citationList"}
            if (ua.indexOf('QQ/') > -1) {
                qqJump(targetUrl);
                return;
            }

            // 微信环境处理‌:ml-citation{ref="4,5" data="citationList"}
            if (ua.indexOf('MicroMessenger') > -1) {
                document.body.innerHTML = `
                    <div class="wechat-mask">
                        <div class="tip-box">
                            <h3>请点击右上角<br>选择「浏览器打开」</h3>
                            <a href="${targetUrl}" class="direct-link">直接访问链接</a>
                        </div>
                    </div>
                `;
                return;
            }

            // 其他环境直接跳转
            window.location.href = targetUrl;
        })();
    </script>
    <style>
        .wechat-mask {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.9);
            z-index: 9999;
        }
        .tip-box {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: #fff;
            padding: 25px 40px;
            border-radius: 12px;
            text-align: center;
        }
        .direct-link {
            display: block;
            margin-top: 15px;
            color: #06c;
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <!-- 默认内容显示 -->
    <h1>正在检测访问环境...</h1>
</body>
</html>
