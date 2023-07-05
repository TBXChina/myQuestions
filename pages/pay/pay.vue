<template>
    <view class="tPay">
        <view class="topBlock"></view>
        <view class="tTop">
            <view class="tTitle">测试报告</view>
            <view class="tDesc">想看更了解自己吗</view>
        </view>
    </view>
</template>

<script>
    export default {
        data() {
            return {

            };
        }
    }
</script>

<style lang="scss" scoped>
    .tPay {
        //background-image: url("../../static/images/bg-1.jpg");
        background-color: #d9e8f1;
        height: 100vh;

        //border: 5px solid #d9e8f1;
        .topBlock {
            height: 1rpx;
        }

        .tTop {
            display: flex;
            flex-direction: column;
            background-color: white;
            height: 12%;
            border-radius: 30rpx 30rpx 0 0;
            margin: 50rpx 10rpx 0rpx 10rpx;
            justify-content: center;
            //align-items: center;
            //border: 5px solid red;

            .tTitle {
                font-size: 50rpx;
                padding: 0rpx 0rpx 0rpx 10rpx;
                //border: 5px solid red;
            }

            .tDesc {
                font-size: 30rpx;
                margin: 10rpx 0 0 10rpx;
                //padding: 0rpx 30rpx;
                //border: 5px solid red;
            }
        }
    }
</style>