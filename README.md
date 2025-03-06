<html>

<head>

    <meta charset="UTF-8">

    <title>跳转中...</title>

</head>

<body>
    
<script>

        // 判断是否在微信内

        function isWechat() {
 
           return /
MicroMessenger/i.
test(navigator.userAgent);

        }


        // 目标链接（加密或动态生成）

        const targetUrl = "https://www.qq.com";



        if (isWechat()) {
  
          // 微信内显示提示页，引导用户浏览器打开

            window.location.href = "/warning-page.html"; 
// 提示页

        } else {
  
          // 非微信环境直接跳转
 
           window.location.href = targetUrl;

        }
 
   </script>

</body>

</html>
