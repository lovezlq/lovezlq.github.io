<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>环境检测示例</title>
    <style>
        .browser-tip {
            padding: 20px;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            background: #f8f9fa;
            text-align: center;
            margin: 50px auto;
            max-width: 600px;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <!-- 默认显示的内容（非QQ/微信环境可见） -->
    <div id="normalContent">
        <h1>欢迎访问正常页面</h1>
        <p>当前为浏览器环境，可完整浏览内容。</p>
    </div>

    <!-- 仅在QQ/微信内显示的提示（默认隐藏） -->
    <div id="qqWechatTip" class="hidden">
        <div class="browser-tip">
            <h2>⚠️ 检测到您在QQ/微信内打开</h2>
            <p>请点击右上角菜单，选择「在浏览器打开」以获得最佳体验</p>
            <button onclick="copyUrl()">复制链接</button>
        </div>
    </div>

    <script>
        // 检测是否在QQ或微信内置浏览器中
        function isInQQWechat() {
            const ua = navigator.userAgent.toLowerCase();
            return ua.match(/qq\//i) || ua.match(/micromessenger\//i);
        }

        // 根据环境显示/隐藏内容
        function checkBrowserEnv() {
            const normalDiv = document.getElementById('normalContent');
            const tipDiv = document.getElementById('qqWechatTip');

            if (isInQQWechat()) {
                // 如果是QQ/微信环境：隐藏正常内容，显示提示
                normalDiv.classList.add('hidden');
                tipDiv.classList.remove('hidden');
            } else {
                // 非QQ/微信环境：正常显示内容
                normalDiv.classList.remove('hidden');
                tipDiv.classList.add('hidden');
            }
        }

        // 复制当前链接（用于提示页按钮）
        function copyUrl() {
            const input = document.createElement('input');
            input.value = window.location.href;
            document.body.appendChild(input);
            input.select();
            document.execCommand('copy');
            document.body.removeChild(input);
            alert('链接已复制到剪贴板');
        }

        // 页面加载时立即检测
        checkBrowserEnv();
    </script>
</body>
</html>
