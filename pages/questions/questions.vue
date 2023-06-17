<template>
    <view class="main">
        <view class="tQuestion">{{question.content}}</view>
        <view class="choices">
            <view v-for="choice in question.choices">
                <view class="ch">
                    <choice-item :content="choice" :isActive="isActive"></choice-item>
                </view>
            </view>
        </view>
        <view class="tPreButton">
            <u-button type="primary" text="上一题"></u-button>
        </view>
    </view>
</template>

<script>
    export default {
        data() {
            return {
                isActive: false,
                question: {
                    content: "问题",
                    choices: [
                        "选项1",
                        "选项2",
                        "选项3",
                        "选项4"
                    ]
                }
            };
        }
    }
</script>

<style lang="scss">
    .main {
        background-image: url("../../static/images/bg-img.png");
        height: 100vh;

        .tQuestion {
            margin: 0 auto;
            text-align: center;
        }

        .tPreButton {
            width: 15%;
            margin: 10rpx 10%;
        }

        .choices {
            .ch {
                margin: 10rpx 10%;
            }
        }
    }
</style>