<template>
  <div class="flex flex-col p-6 bg-gray-900 rounded-lg gap-y-6">
    <div class="flex justify-between items-center">
      <h2 class="text-xl font-semibold leading-loose text-white">Most Artist Played</h2>
      <button class="flex gap-x-2.5 py-3 px-4 rounded-lg border border-gray-700">
        <ChevronDownIcon />
        <span class="text-sm text-white">Today</span>
      </button>
    </div>
    <hr class="border-gray-700" />
    <div class="flex flex-col gap-y-4">
      <div v-for="order in mostOrdered" class="flex gap-x-4 items-center">
        <!-- <img class="w-14 h-14" :src="`/img/${order.image}`" alt="" /> -->
        <div class="font-bold text-gray-700 rounded-full bg-white flex items-center justify-center w-12 h-12">{{ order.short }}</div>
        <div class="flex flex-col gap-y-0.5">
          <div class="text-sm font-medium text-white">{{ order.name }}</div>
          <div class="text-xs text-gray-500">{{ order.count }} times played</div>
        </div>
      </div>
    </div>
    <button class="py-3.5 rounded-lg w-full border border-primary text-primary text-sm font-semibold">View all</button>
  </div>
</template>

<script setup>
  import ChevronDownIcon from "../icons/chevron-down.svg";

  const mostOrdered = [
    {
      name: "Swedish House Mafia",
      short: "SHM",
      image: "food-1.png",
      count: 200,
    },
    {
      name: "Lady Gaga",
      short: "LG",
      image: "food-2.png",
      count: 120,
    },
    {
      name: "Jay-Z",
      short: "JZ",
      image: "food-3.png",
      count: 80,
    },
  ];
</script>
