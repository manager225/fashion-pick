<script setup>
import ItemCard from './ItemCard.vue';

const props = defineProps({
  items: {
    type: Array,
    required: true
  },
  selectedItems: {
    type: Array,
    required: true
  },
  onItemClick: {
    type: Function,
    required: true
  }
});

const isSelected = (item) => {
  return props.selectedItems.some(selectedItem => selectedItem.id === item.id);
};
</script>

<template>
  <div class="items-container">
    <h2>Ваши вещи</h2>
    <div class="items-grid">
      <ItemCard
        v-for="item in items"
        :key="item.id"
        :item="item"
        :selected="isSelected(item)"
        :onClick="onItemClick"
      />
    </div>
  </div>
</template>

<style scoped>
.items-container {
  padding: 15px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: white;
}

h2 {
  margin-top: 0;
  margin-bottom: 15px;
  color: #333;
  font-size: 1.2rem;
}

.items-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  gap: 10px;
}
</style>
