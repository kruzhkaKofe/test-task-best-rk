<template>
  <input
    type="text"
    :value="modelValue"
    @input="updateInput"
    class="input"
    placeholder="Поиск по категориям"
  />
</template>

<script setup>
const props = defineProps({
  modelValue: [String, Number],
});

const emit = defineEmits(["update:modelValue"]);

const updateInput = (event) => {
  emit("update:modelValue", event.target.value);
};
</script>

<style lang="sass" scoped>
.input
  min-width: 100%
  min-height: 35px
  padding: 5px 10px
  border: none
  background-color: hsl(0, 0%, 91%)
  border-radius: 10px
  outline-color: hsl(190, 84%, 75%)
</style>
