<script setup>
const props = defineProps({
  selectedItem: {
    type: Object,
    default: null
  }
});
</script>

<template>
  <div class="selected-item-container">
    <h2>Выбранная вещь</h2>
    <div class="selected-item-content">
      <div v-if="selectedItem" class="selected-item">
        <div class="item-id">ID: {{ selectedItem.id }}</div>
        <div class="item-name">{{ selectedItem.name }}</div>
      </div>
      <div v-else class="empty-message">
        Выберите вещь из списка ниже
      </div>
    </div>
  </div>
</template>

<style scoped>
.selected-item-container {
  padding: 15px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: white;
  height: 100%;
}

h2 {
  margin-top: 0;
  margin-bottom: 15px;
  color: #333;
  font-size: 1.2rem;
}

.selected-item-content {
  display: flex;
  justify-content: center;
  align-items: center;
  height: calc(100% - 50px);
}

.selected-item {
  text-align: center;
  padding: 20px;
  border: 1px solid #e8e8e8;
  border-radius: 8px;
  background-color: #f5f5f5;
  width: 100%;
}

.item-id {
  color: #999;
  margin-bottom: 5px;
  font-size: 0.9rem;
}

.item-name {
  font-size: 1.5rem;
  font-weight: bold;
  color: #1890ff;
}

.empty-message {
  color: #999;
  font-style: italic;
  text-align: center;
}
</style>
