<template>
  <ul>
    <li :class="{ active: activeOption === 'poor' }">
      <button @click="activate('poor')" type="button">Poor</button>
    </li>
    <li :class="{ active: activeOption === 'average' }">
      <button @click="activate('average')" type="button">Average</button>
    </li>
    <li :class="{ active: activeOption === 'great' }">
      <button @click="activate('great')" type="button">Great</button>
    </li>
  </ul>
</template>
<script>
export default {
  props: ['modelValue'],
  data() {
    return {
      activeOption: this.modelValue,
    };
  },
  methods: {
    activate(option) {
      this.activeOption = option;
      this.$emit('update:modelValue', option);
    },
  },
};
</script>
<style scoped>
.active {
  border-color: #e35000;
}
.active button {
  color: #e35000;
  outline: none;
}

ul {
  list-style: none;
  padding: 0;
  display: flex;
  margin: 1.5rem 0;
}

li {
  padding: 1rem;
  margin: 0 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid #ccc;
  border-radius: 10px;
}

button {
  border: none;
  background: transparent;
  cursor: pointer;
}
</style>
