<template>
  <carousel
    v-if="carouselContents && carouselContents?.length > 0"
    :contents="carouselContents"
  />
</template>

<script lang="ts" setup>
import Carousel from "./Carousel.vue";
import { getNews } from "@/apis/notice/notice";
import { StorageKeys } from "@/utils/const";
import { News } from "@/apis/schemas";
import { ref } from "vue";
import { getPrefetchData } from "@/apis/prefetch";
import { carouselData } from "@/utils/csData";

const carouselContents = ref<News[]>();
carouselContents.value = carouselData;
console.log(carouselData);
console.log(carouselContents);
const communityId = uni.getStorageSync(StorageKeys.CommunityId);
// getPrefetchData({ communityId: communityId })
//   .then((res) => {
//     if (!res.getNewsResp?.news) {
//       return Promise.reject("预拉取数据不含轮播图");
//     }
//     carouselContents.value = res.getNewsResp.news;
//     res.getNewsResp = undefined;
//   })
//   .catch(() => {
//     getNews({ communityId: communityId }).then((res) => {
//       carouselContents.value = res.news;
//     });
//   });
</script>

<style lang="scss" scoped></style>
