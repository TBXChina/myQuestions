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

<style lang="scss">
    .ctx {
        font-size: 30rpx;
        border-radius: 20rpx;
        //border: 1px solid black;

        &.active {
            background-color: #ff0000
        }
    }
</style>