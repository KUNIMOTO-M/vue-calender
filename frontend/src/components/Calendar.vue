<template>
<div>
  <h1 class="text-h1">Calender</h1>
  <v-list>
    <v-list-item v-for="event in events" :key="event.id">
      {{ event.name }}
    </v-list-item>  
  </v-list>
  <p>events:</p>
  <p>{{ events }}</p>
  <v-btn type="submit" v-on:click="fetchEvents">Fetchevents</v-btn>

</div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';

export default {
  name: 'Calendar',
  computed: {
    ...mapGetters('events', ['events']),
  },
  methods: {
    ...mapActions('events', ['fetchEvents'])
  }
};
</script>
