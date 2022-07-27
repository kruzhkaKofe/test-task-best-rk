<template>
  <div class="header__input-wrapper">
    <search-input class="header__input" v-model="search" />
  </div>
  <div
    class="header__swiper-wrapper"
    :class="{
      'header__swiper-wrapper--hiden': hideTabs,
    }"
  >
    <swiper class="header__swiper" :slidesPerView="'auto'" :spaceBetween="10">
      <swiper-slide
        v-for="(category, idx) in categories"
        :key="idx"
        class="header__slide"
      >
        <sort-tab
          @check="check"
          :category="category"
          :checkedTab="checkedTab"
        />
      </swiper-slide>
    </swiper>
  </div>
</template>

<script setup>
import SearchInput from "./UI/SearchInput.vue";
import SortTab from "./UI/SortTab.vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import { ref } from "@vue/reactivity";
import { onMounted, onUnmounted } from "@vue/runtime-core";

const props = defineProps({
  search: [Number, String],
  categories: Array,
  checkedTab: String,
  hideTabs: {
    type: Boolean,
    default: false,
  },
});

const emit = defineEmits(["check", "isHide"]);

const check = (category) => {
  emit("check", category);
};

const tabs = document.querySelector(".header__swiper");
let scrollValueY = window.scrollY;

const scrollHandler = () => {
  if (scrollValueY < window.scrollY) {
    emit("isHide", true);
  } else {
    emit("isHide", false);
  }
  scrollValueY = window.scrollY;
};

onMounted(() => {
  window.addEventListener("scroll", scrollHandler);
});

onUnmounted(() => {
  window.removeEventListener("scroll", scrollHandler);
});
</script>

<style lang="sass" scoped>
.header

  &__input-wrapper
    position: fixed
    top: 0
    left: 0
    z-index: 10
    background-color: #FFFFFF
    width: 100vw
    padding: 0.8rem
    box-shadow: none

  &__swiper-wrapper
    position: fixed
    padding: 0.8rem
    top: 60px
    width: 100vw
    background-color: #FFFFFF
    transition: transform 0.4s
    z-index: 5

    &--hiden
      transform: translateY(-70px)

  &__slide
    width: auto
</style>
