<script setup lang="ts">
import type { Event } from '@/types'

// ใช้รูปแบบการเปิดรับ Props แบบเดียวกับ EventCard.vue เป๊ะๆ
defineProps<{
  event: Event
}>()
</script>

<template>
  <div class="event-class">
    <div class="event-info">
      <h1>{{ event.category }}</h1>
      <h1>{{ event.organizer }}</h1>
    </div>
  </div>
</template>

<style scoped>

  .event-class {
    display: flex;
    justify-content: center;
  }

  .event-info {
    padding: 20px;
    width: 250px;
    cursor: pointer;
    border: 1px solid #39495c;
    margin-bottom: 18px;
    text-align: right; 
  }

  .event-info:hover {
    transform: scale(1.01);
    box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
  }

  h1 {
    font-size: 16px;
  }
</style>