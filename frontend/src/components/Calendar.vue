<template>
<div>
  <h1>Calendar</h1>
  <p>events:</p>
  <p>{{ events }}</p>
  <button type="submit" v-on:click="fetchEvents"></button>

  <CalendarDetails />
</div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';
import CalendarDetails from './CalendarDetails.vue';

export default {
  name: 'Calendar',
  components: {
    CalendarDetails
  },
  computed: {
    ...mapGetters('events', ['events']),
  },
  methods: {
    ...mapActions('events', ['fetchEvents'])
  }
};
</script>
