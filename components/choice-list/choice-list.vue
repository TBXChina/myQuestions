<template>
    <view class="choice-list">
        <view v-for="content in choices">
            <view class="choice">
                {{content}}
            </view>
        </view>
    </view>
</template>

<script>
    export default {
        name: "choice-list",
        props: {
            choices: {
                type: Array,
                default () {
                    return []
                }
            }
        },
        data() {
            return {
                alphabetNumber: 65, //A对应的数字，方便递增 String.fromCharCode(65)
            };
        }
    }
</script>

<style lang="scss">
    .choice-list {
        //border: 5px solid green;

        .choice {
            font-size: 50rpx;
            border-radius: 20rpx;
            background-color: #ffffff;
            padding: 10rpx;
            margin: 50rpx 0rpx;

            &.active {
                background-color: #ff0000
            }
        }
    }
</style>