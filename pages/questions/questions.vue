<template>
    <view class="main">
        <view class="topBlock"></view>
        <view class="tQuestion">{{questionNo + 1}}.{{questions[questionNo].content}}</view>
        <view class="process">
            <u-line-progress :percentage="calPercent()" height="30rpx"></u-line-progress>
        </view>
        <!--
        <view class="tChoices">
            <choice-list :choices="questions[questionNo].choices" :activeNo="ansRecords[questionNo]"
                @clickChoicEvent="processClickChoicEvent"></choice-list>
        </view>
        -->

        <view class="tChoices">
            <view v-for="(item, index) in questions[questionNo].choices">
                <view class="tChoice" @click="pickChoice(index)">
                    <choice-item :content="String.fromCharCode(65+index) + '.' + item"
                        :isActive="activeChoice(index)"></choice-item>
                </view>
            </view>
        </view>
        <view class="tQuestionButton">
            <u-button type="primary" color="black" text="上一题" @click="preQuestion"></u-button>
        </view>
        <view v-show="showNextButton()" class="tQuestionButton">
            <u-button type="primary" color="black" text="下一题" @click="nextQuestion"></u-button>
        </view>
        <view v-show="showReportButton()" class="tReportButton">
            <u-button type="primary" color="black" text="查看报告" @click="clickToReport"></u-button>
        </view>
    </view>
</template>

<script>
    export default {
        data() {
            return {
                questionNo: 0,
                questions: [{
                        content: "虚线边框个虚线边框个虚线边框",
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
                    },
                    {
                        content: "第三个问题",
                        choices: [
                            "第三个问题选项1",
                            "第三个问题选项2",
                            "第三个问题选项3",
                            "第三个问题选项4"
                        ]
                    }
                ],
                ansRecords: []
            };
        },
        methods: {
            preQuestion() {
                if (this.questionNo > 0) {
                    this.questionNo = this.questionNo - 1;
                }
            },
            nextQuestion() {
                if (this.questionNo + 1 < this.questions.length) {
                    this.questionNo = this.questionNo + 1;
                }
            },
            activeChoice(index) {
                return index == this.ansRecords[this.questionNo];
            },
            processClickChoicEvent(index) {
                this.ansRecords[this.questionNo] = index;
                this.$forceUpdate();
                this.nextQuestion();
            },
            pickChoice(index) {
                this.ansRecords[this.questionNo] = index;
                this.$forceUpdate();
                setTimeout(() => {
                    this.nextQuestion()
                }, 100)

            },
            calPercent() {
                return Math.floor((this.questionNo + 1) * 100 / this.questions.length);
            },
            clickToReport() {
                uni.navigateTo({
                    url: "/pages/report/report"
                })
            },
            showNextButton() {
                return false;
            },
            showReportButton() {
                return (this.questionNo + 1 == this.questions.length) && this.ansRecords[this.questionNo] != null;
            }
        }
    }
</script>

<style lang="scss" scoped>
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
            display: flex;
            margin: 0 auto;
            width: 80%;
            height: 20%;
            font-size: 60rpx;
            font-family: dingding;
            align-items: center;
            justify-content: center;
            //border: 5px solid red;
        }

        .tChoices {
            margin: 30rpx auto;
            //border: 5px solid red;
            width: 95%;
        }

        .tChoice {
            margin: 15rpx auto;
        }

        .tQuestionButton {
            width: 45%;
            margin: 5rpx 5%;
            //border: 5px solid red;
        }

        .tReportButton {}
    }
</style>