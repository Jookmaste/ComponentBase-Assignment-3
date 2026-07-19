<script setup lang="ts">
  import EventCard from '@/components/EventCard.vue'
  import EventInfo from '@/components/EventInfo.vue'
  import StudentCard from '@/components/StudentCard.vue'
  import type { Event } from '@/types'
  import type {Student} from '@/types'
  import { ref, onMounted } from 'vue'
  import EventService from '@/services/EventService'
  import StudentService from '@/services/StudentService'

  const events = ref<Event[] | null>(null)
  const students = ref<Student[] | null>(null)

  onMounted(() => {
    StudentService.getStudents()
      .then((response) => {
        students.value = response.data
        console.log(response.data)
      })
      .catch((error) => {
        console.error('There was an error!', error)
      })

    EventService.getEvents()
      .then((response) => {
        events.value = response.data
        console.log(response.data)
      })
      .catch((error) => {
        console.error('There was an error!', error)
      })
  })
</script>

<template>

  <h1>Event For Good</h1>
  <div class="event">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
    <EventInfo v-for="event in events" :key="event.id" :event="event" />
  </div>

  <hr />

  <h1>Student List</h1>
  <div class="event">
    <StudentCard v-for="student in students" :key="student.id" :student="student" />
  </div>

</template>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
