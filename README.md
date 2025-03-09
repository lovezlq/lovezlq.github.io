<html>
<head>
    <meta charset="UTF-8">
    <title>请使用外部浏览器打开</title>
    <style>
        .browser-mask {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 9999;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .browser-alert {
            background: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            max-width: 80%;
        }
        .browser-alert button {
            background: #007bff;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            margin: 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <!-- 正常网页内容 -->
    
    <script>
        // 检测QQ和微信内置浏览器
        const ua = navigator.userAgent.toLowerCase();
        const isWeChat = /micromessenger/.test(ua);
        const isQQ = /qq\//.test(ua) || /mobile\s*QB/.test(ua);

        if (isWeChat || isQQ) {
            // 创建提示遮罩层
            const mask = document.createElement('div');
            mask.className = 'browser-mask';
            mask.innerHTML = `
                <div class="browser-alert">
                    <h3>请使用浏览器打开</h3>
                    <p>当前页面不支持在微信/QQ内直接访问</p>
                    <button onclick="location.href='https://www.baidu.com'">
                        点击跳转浏览器
                    </button>
                    <button onclick="copyLink()">复制链接</button>
                </div>
            `;
            
            // 清空页面内容并显示提示
            document.body.innerHTML = '';
            document.body.appendChild(mask);
            
            // 复制链接功能
            function copyLink() {
                const input = document.createElement('input');
                input.value = window.location.href;
                document.body.appendChild(input);
                input.select();
                document.execCommand('copy');
                document.body.removeChild(input);
                alert('链接已复制，请粘贴到浏览器打开');
            }
        }
    </script>
</body>
</html>
