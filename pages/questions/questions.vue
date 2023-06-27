<template>
    <view class="main">
        <view class="topBlock"></view>
        <view class="tQuestion">{{questions[questionNo].content}}</view>
        <view class="process">
            <u-line-progress :percentage="30" height="30rpx"></u-line-progress>
        </view>
        <view class="choices">
            <choice-list :choices="questions[questionNo].choices"></choice-list>
        </view>
        <view class="tPreButton">
            <u-button type="primary" color="black" text="上一题" @click="preClick"></u-button>
        </view>
        <view class="tPreButton">
            <u-button type="primary" color="black" text="下一题" @click="nextClick"></u-button>
        </view>
    </view>
</template>

<script>
    export default {
        data() {
            return {
                questionNo: 0,
                questions: [{
                        content: "默认无边框 dotted: 定义一个点线边框 dashed: 定义一个虚线边框个虚线边框个虚线边框",
                        choices: [
                            "选项1",
                            "选项2",
                            "选项3",
                            "选项4"
                        ]
                    },
                    {
                        content: "第二个问题",
                        choices: [
                            "第二个问题选项1",
                            "第二个问题选项2",
                            "第二个问题选项3",
                            "第二个问题选项4"
                        ]
                    }
                ]
            };
        },
        methods: {
            preClick() {
                if (this.questionNo > 0) {
                    this.questionNo = this.questionNo - 1;
                }
            },
            nextClick() {
                if (this.questionNo < this.questions.length) {
                    this.questionNo = this.questionNo + 1;
                }
            }
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
            margin: 30rpx auto;
            //border: 5px solid red;
            width: 95%;
        }

        .tPreButton {
            width: 45%;
            margin: 5rpx 5%;
            //border: 5px solid red;
        }
    }
</style>