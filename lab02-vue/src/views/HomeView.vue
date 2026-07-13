<script setup lang="ts">
import EventCard from '@/components/EventCard.vue'
import eventsData from '../events.json' 
</script>

<template>
  <div class="home">

    <EventCard 
      v-for="event in eventsData" 
      :key="event.id" 
      :event="event" 
    />
  </div>
</template>