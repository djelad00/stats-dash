<template>
  <div class="p-6 bg-gray-900 rounded-lg">
    <div class="flex justify-between items-center pb-4">
      <h2 class="text-xl font-semibold leading-loose text-white">Top Songs</h2>
      <button class="flex py-3 px-4 rounded-lg border border-gray-700 gap-x-2.5">
        <OptionsIcon />
        <span class="text-sm text-white">Filter songs</span>
      </button>
    </div>
    <table class="w-full">
      <thead>
        <tr class="text-sm font-semibold text-white">
          <td class="py-4 border-b border-gray-700">Artist</td>
          <td class="py-4 border-b border-gray-700">Title</td>
          <td class="py-4 border-b border-gray-700 text-right">Total Plays</td>
          <td class="py-4 border-b border-gray-700 text-center">Genre</td>
        </tr>
      </thead>
      <tbody>
        <tr v-for="order in orders" class="text-sm text-gray-500">
          <td class="py-4">
            <div class="flex gap-4 items-center">
              <img width="32" :src="`/img/${order.avatar}`" alt="" />
              <span> {{ order.name }} </span>
            </div>
          </td>
          <td class="py-4">{{ order.menu }}</td>
          <td class="py-4 tabular-nums text-right">{{ order.total }}</td>
          <td class="py-4 flex justify-center">
            <span
              class="flex justify-center py-1 w-24 font-medium capitalize rounded-full"
              :class="{
                'bg-accent-green/20 text-accent-green': order.status === 'House',
                'bg-accent-purple/20 text-accent-purple': order.status === 'Pop',
                'bg-accent-orange/20 text-accent-green': order.status === 'Rock',
              }"
            >
              {{ order.status }}
            </span>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
  import OptionsIcon from "../icons/options.svg";

  const orders = [
    {
      avatar: "avatar-1.png",
      name: "Swedish House Mafia",
      menu: "Save the world",
      total: "225",
      status: "House",
    },
    {
      avatar: "avatar-2.png",
      name: "Michael Jackson",
      menu: "The way you make me feel (remix)",
      total: "145",
      status: "Pop",
    },
    {
      avatar: "avatar-3.png",
      name: "LMFAO vs Metallica",
      menu: "Shots! (Heavy Rock remix)",
      total: "105",
      status: "Rock",
    },
    {
      avatar: "avatar-4.png",
      name: "Daft Punk",
      menu: "One more time (Baltimore House edit)",
      total: "85",
      status: "House",
    },
    {
      avatar: "avatar-5.png",
      name: "Doja Cat",
      menu: "Say so",
      total: "56",
      status: "Pop",
    },
    {
      avatar: "avatar-6.png",
      name: "Journey",
      menu: "Don't stop believing",
      total: "45",
      status: "Rock",
    },
  ];
</script>
