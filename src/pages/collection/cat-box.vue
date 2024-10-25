<template>
  <view class="cats-box">
    <image :src="teacher.imgUrl" class="avatar" mode="aspectFill" />
    <view class="text">
      <view class="title">{{ teacher.name }}</view>
      <view class="details">
        <view class="info">职称：{{ teacher.title }}</view>
        <view class="info">办公室：{{ teacher.office }}</view>
        <view class="info">办公电话：{{ teacher.phone }}</view>
        <view class="info">邮箱：{{ teacher.email }}</view>
      </view>
    </view>
  </view>
</template>

<script lang="ts" setup>
import { Teacher } from "@/apis/schemas";

const props = defineProps<{
  teacher: Teacher;
}>();
</script>

<style lang="scss" scoped>
.cats-box {
  width: 700upx;
  height: 200upx;
  border-radius: 36upx;
  display: flex;
  align-items: center;
  justify-content: left;
  position: relative;
  background-color: #ffffff;
  box-shadow: 0 0 8upx rgba(0, 0, 0, 0.1);
  margin: 0 auto 12upx;

  .avatar {
    width: 174upx;
    height: 174upx;
    border-radius: 24upx;
    margin-left: 24upx;
    margin-right: 40upx;
  }

  .text {
    flex: 1;
    margin-right: 64upx;
    height: 144upx;
    display: flex;
    flex-direction: column;
    justify-content: space-between;

    .title {
      font-size: 36upx;
      color: #1d1d1d;
    }

    .details {
      font-size: 20upx;
      color: #939393;

      .info {
      }
    }
  }

  .star {
    position: absolute;
    right: 36upx;
    top: 36upx;
    width: 30upx;
    height: 30upx;
    background-size: 100% 100%;
    background-image: url("/static/images/star-grey.png");

    &.collected {
      background-image: url("/static/images/star-yellow.png");
    }
  }
}
</style>
