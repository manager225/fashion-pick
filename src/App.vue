<script setup>
import { ref } from 'vue';
import UserItemsList from './components/UserItemsList.vue';
import AvailableItemsList from './components/AvailableItemsList.vue';
import SelectedUserItems from './components/SelectedUserItems.vue';
import SelectedAvailableItem from './components/SelectedAvailableItem.vue';

// Данные для левого блока (вещи пользователя)
const userItems = ref([
  { id: 1, name: "Shoes 1" },
  { id: 2, name: "Shoes 2" },
  { id: 3, name: "Shoes 3" },
  { id: 4, name: "Shoes 4" },
  { id: 5, name: "T-shirt 1" },
  { id: 6, name: "T-shirt 2" },
  { id: 7, name: "T-shirt 3" },
  { id: 8, name: "T-shirt 4" }
]);

// Данные для правого блока (вещи на выбор)
const availableItems = ref([
  { id: 11, name: "Jacket 1" },
  { id: 12, name: "Jacket 2" },
  { id: 13, name: "Jacket 3" },
  { id: 14, name: "Jacket 4" },
  { id: 15, name: "Hoodie 1" },
  { id: 16, name: "Hoodie 2" },
  { id: 17, name: "Hoodie 3" },
  { id: 18, name: "Hoodie 4" }
]);

// Выбранные вещи пользователя (левый верхний блок)
const selectedUserItems = ref([]);

// Выбранная вещь из доступных (правый верхний блок)
const selectedAvailableItem = ref(null);

// Обработчик клика по вещи пользователя
const handleUserItemClick = (item) => {
  const index = selectedUserItems.value.findIndex(selectedItem => selectedItem.id === item.id);

  if (index !== -1) {
    // Если вещь уже выбрана, удаляем её из выбранных
    selectedUserItems.value.splice(index, 1);
  } else {
    // Если вещь не выбрана и количество выбранных меньше 6, добавляем её
    if (selectedUserItems.value.length < 6) {
      selectedUserItems.value.push(item);
    }
  }
};

// Обработчик клика по доступной вещи
const handleAvailableItemClick = (item) => {
  if (selectedAvailableItem.value && selectedAvailableItem.value.id === item.id) {
    // Если вещь уже выбрана, снимаем выбор
    selectedAvailableItem.value = null;
  } else {
    // Иначе выбираем эту вещь
    selectedAvailableItem.value = item;
  }
};
</script>

<template>
  <div class="app-container">
    <h1>Выбор вещей</h1>

    <div class="top-section">
      <div class="top-left">
        <SelectedUserItems :selectedItems="selectedUserItems" />
      </div>
      <div class="top-right">
        <SelectedAvailableItem :selectedItem="selectedAvailableItem" />
      </div>
    </div>

    <div class="bottom-section">
      <div class="bottom-left">
        <UserItemsList
          :items="userItems"
          :selectedItems="selectedUserItems"
          :onItemClick="handleUserItemClick"
        />
      </div>
      <div class="bottom-right">
        <AvailableItemsList
          :items="availableItems"
          :selectedItem="selectedAvailableItem"
          :onItemClick="handleAvailableItemClick"
        />
      </div>
    </div>
  </div>
</template>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f0f2f5;
  color: #333;
}
</style>

<style scoped>
.app-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

h1 {
  text-align: center;
  margin-bottom: 30px;
  color: #1890ff;
}

.top-section, .bottom-section {
  display: flex;
  gap: 20px;
  margin-bottom: 20px;
}

.top-left, .top-right, .bottom-left, .bottom-right {
  flex: 1;
  min-height: 200px;
}

.top-section {
  min-height: 250px;
}

@media (max-width: 768px) {
  .top-section, .bottom-section {
    flex-direction: column;
  }
}
</style>
