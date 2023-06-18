<template>
    <view class="main">
        <view class="topBlock"></view>
        <view class="tQuestion">{{question.content}}</view>
        <view class="process">
            <u-line-progress :percentage="30" height="30rpx"></u-line-progress>
        </view>
        <view class="choices">
            <view v-for="choice in question.choices">
                <view class="ch">
                    <choice-item :content="choice" :isActive="isActive"></choice-item>
                </view>
            </view>
        </view>
        <view class="tPreButton">
            <u-button type="primary" color="black" text="上一题"></u-button>
        </view>
    </view>
</template>

<script>
    export default {
        data() {
            return {
                isActive: false,
                question: {
                    content: "默认无边框 dotted: 定义一个点线边框 dashed: 定义一个虚线边框个虚线边框个虚线边框",
                    choices: [
                        "A. 选项1",
                        "B. 选项2",
                        "C. 选项3",
                        "D. 选项4"
                    ]
                },
                title: String.fromCharCode(66)
            };
        }
    }
</script>

<style lang="scss">
    .main {
        //background-image: url("../../static/images/bg-1.jpg");
        background-color: #ffaa7f;
        height: 100vh;

        .topBlock {
            height: 15%;
        }

        .process {
            margin: 20rpx auto;
            width: 90%;
            //border: 5px solid red;
        }

        .tQuestion {
            margin: 0 auto;
            text-align: center;
            width: 80%;
            font-size: 60rpx;
            font-family: dingding;
        }

        .choices {
            margin: 30rpx;
            //border: 5px solid red;
            width: 90%;

            .ch {
                margin: 50rpx 10rpx;
            }
        }

        .tPreButton {
            width: 45%;
            margin: 5rpx 5%;
            //border: 5px solid red;
        }
    }
</style>