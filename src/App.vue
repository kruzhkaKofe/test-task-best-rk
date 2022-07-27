<template>
  <div class="app">
    <search-header
      :categories="categories"
      :search="search"
      :checkedTab="checkedTab"
      :hideTabs="hideTabs"
      @check="check"
      @isHide="isHide"
    />
    <content-block
      v-for="content in contents"
      :key="content.id"
      :content="content"
    />
  </div>
</template>

<script setup>
import SearchHeader from "./components/SearchHeader.vue";
import ContentBlock from "./components/ContentBlock.vue";
import { ref } from "vue";

const categories = [
  "Подборки",
  "Все категории",
  "Где поесть",
  "Заправки",
  "Развлечения",
  "Больницы",
  "Магазины",
  "Парки",
  "Стадионы",
  "Театры",
];

const contents = [
  {
    id: 1,
    heading: "Самое новое",
    offers: [
      {
        id: 1.1,
        image: "Картинка 1.1",
        description: "Описание 1.1",
      },
      {
        id: 1.2,
        image: "Картинка 1.2",
        description: "Описание 1.2",
      },
      {
        id: 1.3,
        image: "Картинка 1.3",
        description: "Описание 1.3",
      },
      {
        id: 1.4,
        image: "Картинка 1.4",
        description: "Описание 1.4",
      },
      {
        id: 1.5,
        image: "Картинка 1.5",
        description: "Описание 1.5",
      },
      {
        id: 1.6,
        image: "Картинка 1.6",
        description: "Описание 1.6",
      },
    ],
  },
  {
    id: 2,
    heading: "Макимально сэкономить",
    offers: [
      {
        id: 2.1,
        image: "Картинка 2.1",
        description: "Описание 2.1",
      },
      {
        id: 2.2,
        image: "Картинка 2.2",
        description: "Описание 2.2",
      },
      {
        id: 2.3,
        image: "Картинка 2.3",
        description: "Описание 2.3",
      },
      {
        id: 2.4,
        image: "Картинка 2.4",
        description: "Описание 2.4",
      },
      {
        id: 2.5,
        image: "Картинка 2.5",
        description: "Описание 2.5",
      },
      {
        id: 2.6,
        image: "Картинка 2.6",
        description: "Описание 2.6",
      },
    ],
  },
  {
    id: 3,
    heading: "Выгодное предложение",
    offers: [
      {
        id: 3.1,
        image: "Картинка 3.1",
        description: "Описание 3.1",
      },
      {
        id: 3.2,
        image: "Картинка 3.2",
        description: "Описание 3.2",
      },
      {
        id: 3.3,
        image: "Картинка 3.3",
        description: "Описание 3.3",
      },
      {
        id: 3.4,
        image: "Картинка 3.4",
        description: "Описание 3.4",
      },
      {
        id: 3.5,
        image: "Картинка 3.5",
        description: "Описание 3.5",
      },
      {
        id: 3.6,
        image: "Картинка 3.6",
        description: "Описание 3.6",
      },
    ],
  },
  {
    id: 4,
    heading: "Популярное сегодня",
    offers: [
      {
        id: 4.1,
        image: "Картинка 4.1",
        description: "Описание 4.1",
      },
      {
        id: 4.2,
        image: "Картинка 4.2",
        description: "Описание 4.2",
      },
      {
        id: 4.3,
        image: "Картинка 4.3",
        description: "Описание 4.3",
      },
      {
        id: 4.4,
        image: "Картинка 4.4",
        description: "Описание 4.4",
      },
      {
        id: 4.5,
        image: "Картинка 4.5",
        description: "Описание 4.5",
      },
      {
        id: 4.6,
        image: "Картинка 4.6",
        description: "Описание 4.6",
      },
    ],
  },
];

const checkedTab = ref("Подборки");
const hideTabs = ref(false);
const search = ref("");

const check = (category) => {
  checkedTab.value = category;
};

const isHide = (value) => {
  hideTabs.value = value;
};
</script>

<style lang="sass">
*
  margin: 0
  padding: 0
  box-sizing: border-box

body
  padding-top: 130px

.app
  display: flex
  flex-direction: column
  align-items: center
</style>
