<script setup>
const props = defineProps({
  selectedItems: {
    type: Array,
    required: true
  }
});
</script>

<template>
  <div class="selected-items-container">
    <h2>Выбранные вещи пользователя</h2>
    <div class="selected-items-list">
      <div v-if="selectedItems.length === 0" class="empty-message">
        Выберите вещи из списка ниже
      </div>
      <div
        v-for="(item, index) in selectedItems"
        :key="item.id"
        class="selected-item"
      >
        <span class="item-number">{{ index + 1 }}.</span>
        <span class="item-name">{{ item.name }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.selected-items-container {
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

.selected-items-list {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.selected-item {
  padding: 10px;
  border: 1px solid #e8e8e8;
  border-radius: 4px;
  background-color: #f5f5f5;
  display: flex;
  align-items: center;
}

.item-number {
  font-weight: bold;
  margin-right: 10px;
  color: #1890ff;
}

.empty-message {
  color: #999;
  font-style: italic;
  text-align: center;
  padding: 20px 0;
}
</style>
