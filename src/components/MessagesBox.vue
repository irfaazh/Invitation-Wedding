<template>
  <section class="w-10/12 mx-auto mt-6">
    <p>Ada {{ messages.length }} pesan dari para tamu</p>
  </section>
  <section style="max-height: 400px" class="w-10/12 mt-5 mx-auto overflow-scroll">
    <template v-for="(msg, x) in messages" :key="x">
      <div class="w-full mb-5 border-b-2 border-orange-200 pb-1">
        <span class="flex gap-2 items-center">
          <p class="kalam-font text-orange-800 text-xl">{{ msg.guestName }}</p>
          <span class="py-1 px-2 bg-orange-700 text-gray-100 rounded-lg text-xxs">{{ msg.guestStatus }}</span>
        </span>
        <p class="font-medium text-xs mt-2">Pada {{ msg.timestamp }}</p>
        <p class="text-sm">{{ msg.guestMessage }}</p>
      </div>
    </template>
  </section>
</template>

<script setup>
const props = defineProps({
  messages: {
    type: Array,
    default: () => []
  }
})
</script>

<style scoped>
.kalam-font {
  font-family: 'Kalam', cursive;
}

.text-xxs {
  font-size: 0.65rem;
}
</style>