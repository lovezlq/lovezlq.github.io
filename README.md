<script>
// 检测QQ内置浏览器环境‌:ml-citation{ref="2,3" data="citationList"}
if(strpos($_SERVER['HTTP_USER_AGENT'], 'QQ/') !== false) {
    $targetUrl = urlencode('http://'.$_SERVER['HTTP_HOST'].$_SERVER['REQUEST_URI']);
    
    // 输出跳转引导页‌:ml-citation{ref="5,6" data="citationList"}
    echo <<<HTML
<!DOCTYPE html>
<html>
<head>
    <meta http-equiv="refresh" content="0;url=qqbrowser://open?url=$targetUrl">
</head>
<body>
    <script>
        // 兼容性处理：若协议跳转失败则显示操作引导‌:ml-citation{ref="3,4" data="citationList"}
        setTimeout(function(){
            document.body.innerHTML = `
                <div style="text-align:center;padding:20px;">
                    <h3>当前页面需通过外部浏览器访问</h3>
                    <button onclick="window.location.href='$targetUrl'" 
                        style="padding:12px 24px;background:#31A8E6;color:white;border:none;border-radius:8px;">
                        点击手动跳转
                    </button>
                </div>
            `;
        }, 1500);
    </script>
</body>
</html>
HTML;
    exit;
}
?>
</script>
