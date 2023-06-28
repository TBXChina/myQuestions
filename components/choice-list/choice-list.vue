<template>
    <view class="choice-list">
        <view v-for="(content, index) in choices">
            <view class="choice" :class="index == activeNo ? 'active': ''" @click="clickChoice(index)">
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
            },
            activeNo: {
                type: Number,
                default () {
                    return -1;
                }
            }
        },
        data() {
            return {
                alphabetNumber: 65, //A对应的数字，方便递增 String.fromCharCode(65)
            };
        },
        methods: {
            clickChoice(index) {
                this.$emit("clickChoicEvent", index)
            }
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