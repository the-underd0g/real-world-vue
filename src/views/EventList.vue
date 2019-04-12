<template>
    <div>
        <h1>Events Listing</h1>
        <EventCard v-for="event in events" :key="event.id" :event="event"/>
    </div>
</template>

<script>
    import EventCard from '@/components/EventCard.vue';
    import EventService from '@services/EventService.js';

    export default {
        name: "EventList",
        components: {
            EventCard
        },
        data() {
            return {
                events: []
            }
        },
        created() {
            EventService.getEvents('http:://localhost:3000/events')
                .then(response => {
                    this.events = response;
                })
                .catch(error => {
                    console.log(`${error.response}` );
                })
        }
    }


</script>

<style scoped>

</style>