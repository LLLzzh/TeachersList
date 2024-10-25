<template>
  <view v-if="show && cat">
    <image :src="mainImgUrl" class="cat-image" mode="aspectFill" />
    <view class="goBackButton" @click="goBack">
      <view class="left-arrow" />
    </view>
    <view class="main">
      <Header :cat="cat" />
      <MetaInfo :cat="cat" />
    </view>
  </view>
</template>

<script lang="ts" setup>
import { reactive, ref } from "vue";

import Header from "@/pages/cat/header.vue";
import MetaInfo from "@/pages/cat/meta-info.vue";
import { Cat } from "@/apis/schemas";
import { teachers } from "@/utils/csData";

const show = ref(false);
const props = defineProps<{
  id: string;
}>();
const cat = ref<Cat>();
console.log(props);
const mainImgUrl = ref("");
const goBack = () => {
  uni.navigateBack({
    delta: 1
  });
};

const teacher = teachers.find((teacher) => teacher.id == props.id);
show.value = true;
console.log(teacher);
if (teacher) {
  cat.value = teacher;
  mainImgUrl.value = teacher.imgUrl;
}
</script>

<style lang="scss" scoped>
.cat-image {
  position: fixed;
  width: 30vw;
  height: 30vw;
  top: 21vw;
  right: 10vw;
  left: auto;
  border-radius: 15vw;
}

.goBackButton {
  position: fixed;
  width: 10vw;
  height: 10vw;
  border-radius: 5vw;
  background-color: #1d1d1d;
  margin-top: -18vw;
  margin-left: 4vw;
  margin-right: 4vw;
  opacity: 0.3;
  z-index: 10;
}

.left-arrow {
  position: fixed;
  border-width: 1vw 1vw 0 0;
  border-color: #ffffff;
  border-style: solid;
  height: 3vw;
  width: 3vw;
  margin-top: 2.7vw;
  margin-left: 3.5vw;
  margin-right: 3.5vw;
  transform: matrix(-0.71, 0.71, 0.71, 0.71, 0, 0);
  z-index: 11;
}

.main {
  border-radius: 4vw 4vw 0 0;
  margin-top: 30vw;
  width: 100vw;
  background-color: #ffffff;
}
</style>
