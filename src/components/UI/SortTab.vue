<template>
  <div class="tab">
    <input
      type="radio"
      name="category"
      class="tab__radio"
      :id="category"
      :value="category"
      :checked="checkedTab === category"
      @click="check(category)"
    />
    <label class="tab__label" :for="category">{{ category }}</label>
  </div>
</template>

<script setup>
const props = defineProps({
  category: String,
  checkedTab: String,
});

const emit = defineEmits(["check"]);

const check = (category) => {
  emit("check", category);
};
</script>

<style lang="sass" scoped>
.tab
	background-color: #FFFFFF
	border-radius: 10px

	&__radio
		display: none

		&:checked + label
			background: hsl(190, 84%, 75%)

	&__label
		display: inline-block
		padding: 5px 10px
		border: 2px solid hsl(0, 0%, 91%)
		border-radius: 10px
		font-size: 1rem
		cursor: pointer
</style>
