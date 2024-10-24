<template>
  <view class="info">
    <view class="tile" style="width: 16vw">
      <view class="key">性别</view>
      <view class="value">
        {{ props.cat.sex }}
      </view>
    </view>
    <view class="tile" style="width: 30vw">
      <view class="key">专业技术职务</view>
      <view class="value">
        {{ `青年研究员` }}
      </view>
    </view>
    <view class="tile" style="width: 36vw">
      <view class="key">联系电话</view>
      <view class="value">
        {{ `12345678910` }}
      </view>
    </view>
  </view>
  <view class="info">
    <view class="tile" style="width: 49vw">
      <view class="key">毕业院校</view>
      <view class="value">
        {{ `华东师范大学` }}
      </view>
    </view>
    <view class="tile" style="width: 36vw">
      <view class="key">学位</view>
      <view class="value">
        {{ `工学博士` }}
      </view>
    </view>
  </view>
  <view class="info">
    <view class="tile" style="width: 49vw">
      <view class="key">办公地址</view>
      <view class="value">
        {{ `理科大楼A123` }}
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
        {{ `test@cs.ecnu.edu.cn` }}
      </view>
    </view>
  </view>
</template>

<script lang="ts" setup>
import { Cat } from "@/apis/schemas";

interface Props {
  cat: Cat;
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
    }
  }
}
</style>
