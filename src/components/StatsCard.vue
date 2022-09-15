<template>
  <div class="flex gap-6">
    <div v-for="stat in stats" class="flex flex-col p-4 w-1/3 bg-gray-900 rounded-lg gap-y-3">
      <div class="flex items-center gap-x-3">
        <div class="p-2 bg-gray-800 rounded-lg">
          <Component :is="stat.icon" />
        </div>
        <span class="text-xs font-medium" :class="stat.status === 'up' ? 'text-accent-green' : 'text-accent-red'">
          {{ stat.percentage }}
        </span>
        <div class="p-0.5 rounded-full" :class="stat.status === 'up' ? 'bg-accent-green/20' : 'bg-accent-red/20'">
          <ArrowUpIcon v-if="stat.status === 'up'" class="fill-current text-accent-green" />
          <ArrowDownIcon v-else class="fill-current text-accent-red" />
        </div>
      </div>
      <div class="text-3xl font-semibold text-white">{{ stat.value }}</div>
      <div class="text-sm tracking-wide text-gray-500">{{ stat.title }}</div>
    </div>
  </div>
</template>

<script setup>
  import CoinIcon from "../icons/coin.svg";
  import OrderIcon from "../icons/order.svg";
  import CustomerIcon from "../icons/customer.svg";
  import ArrowUpIcon from "../icons/arrow-up.svg";
  import ArrowDownIcon from "../icons/arrow-down.svg";
  const stats = [
    {
      title: "Total Hours",
      percentage: "+32.40%",
      value: "10,243",
      status: "up",
      icon: CoinIcon,
    },
    {
      title: "Total sessions",
      percentage: "-12.40%",
      value: "156",
      status: "down",
      icon: OrderIcon,
    },
    {
      title: "Total songs",
      percentage: "+2.40%",
      value: "534",
      status: "up",
      icon: CustomerIcon,
    },
  ];
</script>
