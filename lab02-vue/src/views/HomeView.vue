<script setup lang="ts">
import EventCard from '@/components/EventCard.vue'
import EventDetails from '@/components/EventDetails.vue'
import eventsData from '../events.json'
</script>

<template>
  <div class="events">

    <div v-for="event in eventsData" :key="event.id">
      <EventCard :event="event" />
      <EventDetails :event="event" />
    </div>
  </div>
</template>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>