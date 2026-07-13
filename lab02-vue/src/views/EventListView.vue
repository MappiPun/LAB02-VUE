<script setup lang="ts">
import EventCard from '@/components/EventCard.vue'
import type { Event } from '@/types'
import { ref, onMounted } from 'vue' 
import axios from 'axios' 

const events = ref<Event[] | null>(null)

onMounted(() => {
  axios.get('https://my-json-server.typicode.com/MappiPun/LAB02-VUE-DB/events')
    .then((response) => {
      console.log(response.data) 
      events.value = response.data 
    })
    .catch((error) => {
      console.error('There was an error!', error)
    })
})
</script>

<template>
  <div class="events">
    
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>