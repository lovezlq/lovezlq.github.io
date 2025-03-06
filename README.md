<!-- 微信环境显示引导提示 ‌:ml-citation{ref="3,4" data="citationList"} -->
<div class="wx-guide" v-if="isWeixin">
    <div class="arrow-icon"></div>
    <p>点击右上角<br/>选择「在浏览器打开」</p>
</div>

<style>
.wx-guide {
    position: fixed;
    background: rgba(0,0,0,0.85);
    color: #fff;
    text-align: center;
    z-index: 9999;
}
</style>
