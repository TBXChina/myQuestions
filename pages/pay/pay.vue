<template>
    <view class="tPay">
        <view class="topBlock"></view>
        <view class="tTop">
            <view class="tTitle">测试报告</view>
            <view class="tDesc">想看更了解自己吗</view>
        </view>
        <view class="tDetail">
            <view class="tKV">
                <view>耗时</view>
                <view>120秒</view>
            </view>
            <view class="tKV">
                <view>性别</view>
                <view>男</view>
            </view>
        </view>
        <view class="tCuxiao">
            <view class="tTitle">您的专属报告已经生成</view>
            <view class="tTitle">支付完成后立刻查看结果</view>
            <view class="tTakePart">已有
                <view style="color: red;">{{personNum}}</view>
                人参与
            </view>
            <view style="margin-bottom: 10rpx;">点击下方支付按钮</view>
        </view>
        <view class="tPayButton">
            <view class="tWePay">微信支付</view>
        </view>
    </view>
</template>

<script>
    export default {
        data() {
            return {
                personNum: 1234
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
            margin: 50rpx 10rpx 10rpx 10rpx;
            justify-content: center;
            //align-items: center;
            //border: 5px solid red;



            .tDesc {
                font-size: 30rpx;
                margin: 10rpx 0 0 10rpx;
                //padding: 0rpx 30rpx;
                //border: 5px solid red;
            }
        }

        .tTitle {
            font-size: 50rpx;
            padding: 0rpx 0rpx 0rpx 10rpx;
            font-weight: bold;
            //border: 5px solid red;
        }

        .tDetail {
            background-color: white;
            //height: 12%;
            border-radius: 0 0 30rpx 30rpx;
            margin: 10rpx 10rpx 0rpx 10rpx;
            padding: 10rpx 0 20rpx 0;

            .tKV {
                display: flex;
                justify-content: space-between;
                padding: 8rpx 10rpx;
            }
        }

        .tCuxiao {
            background-color: white;
            //height: 20%;
            border-radius: 30rpx;
            margin: 30rpx 10rpx;
            text-align: center;
            border: 5px solid red;

            .tTakePart {
                margin: 20rpx;
                display: flex;
                justify-content: center;
                //border: 5px solid blue;
            }
        }

        .tPayButton {
            height: 5%;
            width: 95%;
            border-radius: 20rpx;
            background-color: #36a300;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            align-items: center;

            .tWePay {
                color: white;
            }
        }


    }
</style>