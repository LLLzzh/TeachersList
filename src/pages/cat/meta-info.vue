<template>
  <view class="info">
    <view class="tile" style="width: 49vw">
      <view class="key">联系电话</view>
      <view class="value">
        {{ props.cat.phone }}
      </view>
    </view>
    <view class="tile" style="width: 36vw">
      <view class="key">专业技术职务</view>
      <view class="value">
        {{ props.cat.title }}
      </view>
    </view>
  </view>
  <view class="info">
    <view class="tile" style="width: 49vw">
      <view class="key">毕业院校</view>
      <view class="value">
        {{ props.cat.university }}
      </view>
    </view>
    <view class="tile" style="width: 36vw">
      <view class="key">学位</view>
      <view class="value">
        {{ props.cat.degree }}
      </view>
    </view>
  </view>
  <view class="info">
    <view class="tile" style="width: 49vw">
      <view class="key">办公地址</view>
      <view class="value">
        {{ props.cat.office }}
      </view>
    </view>
    <view class="tile" style="width: 36vw">
      <view class="key">邮编</view>
      <view class="value">
        {{ `200062` }}
      </view>
    </view>
  </view>
  <view class="info">
    <view class="tile" style="width: 88vw">
      <view class="key">通讯地址</view>
      <view class="value">
        {{ `上海市普陀区中山北路3663号` }}
      </view>
    </view>
  </view>
  <view class="info">
    <view class="tile" style="width: 88vw">
      <view class="key">电子邮箱</view>
      <view class="value">
        {{ props.cat.email }}
      </view>
    </view>
  </view>
</template>

<script lang="ts" setup>
import { Cat, Teacher } from "@/apis/schemas";

interface Props {
  cat: Teacher;
}

const props = defineProps<Props>();

// 本页面每个tile的间距是3vw
</script>

<style lang="scss" scoped>
.info {
  margin-left: 6vw;
  margin-top: 3vw;
  width: 88vw;
  display: flex;
  justify-content: space-between;
  .tile {
    border-radius: 2vw;
    background-color: #f7f8fc;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 15vw;
    .key {
      color: #1fa1ff;
      font-size: 3.5vw;
      width: fit-content;
      margin-bottom: 2.5vw;
    }
    .value {
      font-size: 4vw;
      font-weight: bold;
      width: fit-content;
      min-height: 5vw;
    }
  }
}
</style>
