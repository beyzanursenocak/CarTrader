<template>
  <div class="rounded shadow mt-20">
    <CarMessageCard
      v-for="message in messages"
      :key="message.id"
      :message="message"
    />
  </div>
</template>

<script setup>
definePageMeta({
  layout: "custom",
  middleware: ['auth'] //1. yol
});

const route = useRoute();
const { data: messages } = useFetch(`/api/car/listings/${route.params.id}/message`)
</script>