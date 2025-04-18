<script setup>
const props = defineProps({
  item: {
    type: Object,
    required: true
  },
  selected: {
    type: Boolean,
    default: false
  },
  onClick: {
    type: Function,
    required: true
  }
});
</script>

<template>
  <div
    class="item-card"
    :class="{ 'selected': selected }"
    @click="onClick(item)"
  >
    {{ item.name }}
  </div>
</template>

<style scoped>
.item-card {
  padding: 15px;
  margin: 8px;
  border: 1px solid #ddd;
  border-radius: 8px;
  cursor: pointer;
  background-color: #f9f9f9;
  transition: all 0.3s ease;
  text-align: center;
}

.item-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.item-card.selected {
  background-color: #e6f7ff;
  border-color: #1890ff;
  box-shadow: 0 0 0 2px rgba(24, 144, 255, 0.2);
}
</style>
