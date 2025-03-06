<!-- 检测到微信/QQ时显示引导层 ‌:ml-citation{ref="5,6" data="citationList"} -->  
<script>  
if (/MicroMessenger|QQ\//i.test(navigator.userAgent)) {  
    document.getElementById('guideLayer').style.display = 'block';  
}  
</script>  

<!-- 引导层样式 -->  
<style>  
.guide-layer {  
    background: rgba(0,0,0,0.9);  
    position: fixed;  
    top: 0;  
    width: 100%;  
    height: 100%;  
    z-index: 9999;  
}  
</style>  
