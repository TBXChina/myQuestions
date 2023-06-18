<script>
    export default {
        onLaunch: function() {
            console.log('App Launch')
        },
        onShow: function() {
            console.log('App Show')
        },
        onHide: function() {
            console.log('App Hide')
        }
    }
</script>

<style lang="scss">
    @import "@/uni_modules/uview-ui/index.scss";

    /*每个页面公共css */
    @font-face {
        font-family: dingding;
        src: url('~@/static/font/DingTalk_JinBuTi_Regular.ttf');
    }
</style>