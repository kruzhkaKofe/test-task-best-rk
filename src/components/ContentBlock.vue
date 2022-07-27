<template>
  <div class="content">
    <div class="content__header">
      <h2 class="content__heading">{{ content.heading }}</h2>
      <a class="content__view-all" href="#">Смотреть все ❯</a>
    </div>
    <swiper class="content__swiper" :slidesPerView="'auto'" :spaceBetween="10">
      <swiper-slide
        class="content__slide"
        v-for="offer in content.offers"
        :key="offer.id"
      >
        <div class="content__image">
          {{ offer.image }}
        </div>
        <div class="content__description">
          <span>{{ offer.description }}</span>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";

const props = defineProps({
  content: Object,
});
</script>

<style lang="sass" scoped>
.content
	max-width: 100vw
	padding: 1rem

	&__header
		display: flex
		align-items: center
		justify-content: space-between
		margin-bottom: 15px

	&__heading
		font-size: 1rem
		text-align: left

	&__view-all
		font-size: 1rem
		display: flex
		align-items: center

	&__view-all
		text-decoration: none
		color: hsl(190, 84%, 75%)

	&__slide
		width: 250px
		height: 250px
		border-radius: 10px
		border: 2px solid hsl(0, 0%, 91%)

	&__image
		display: flex
		align-items: center
		justify-content: center
		width: 100%
		height: 170px
		border-bottom: 2px solid hsl(0, 0%, 91%)

	&__description
		width: 100%
		height: calc(250px - 170px)
		display: flex
		align-items: center
		justify-content: center
</style>
