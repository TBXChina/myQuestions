<template>
    <view>
        <view class="ctx" :class="isActive ? 'active': ''">
            {{content}}
        </view>

    </view>
</template>

<script>
    export default {
        name: "choice-item",
        props: {
            content: {
                type: String,
                default: ''
            },
            isActive: {
                type: Boolean,
                default: false
            }
        },
        data() {
            return {

            };
        }
    }
</script>

<style lang="scss" scoped>
    .ctx {
        font-size: 50rpx;
        border-radius: 20rpx;
        background-color: #ffffff;
        padding: 10rpx;
        //border: 5px solid red;

        &.active {
            background-color: #ff0000
        }
    }
</style>