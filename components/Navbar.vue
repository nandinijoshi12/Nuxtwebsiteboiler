<template>
  <div class="fixed z-40 flex w-full flex-row items-center justify-center bg-neutral-800/50 py-3 text-neutral-300 backdrop-blur-sm">
    <div class="flex w-full flex-row justify-between">
      <div class=" flex items-center"><img src="" alt=""></div>
      <span v-for="(item, index) in menuitems" :key="index" class="w-1/2">
        <a :href="item.path" class="cursor-pointer hover:text-white">
          <p>{{item.name}}</p>
          <div v-if="'/'+ route.name == item.path" class="absolute bottom-1 flex w-full justify-center">
            <p class="h-1 w-2 rounded-full bg-sky-400"></p>
          </div>
          <div v-else class=""></div>
        </a>
      </span>
    </div>
  </div>
</template>

<script lang="ts" setup>
const route = useRoute()
const isOpen= ref(false)
const menuitems : {
    id: number;
    path: string; 
    name: string; 
  }[]=[
    {
      id: 4,
      path: `/`,
      name: `Home`,
    },
    {
      id: 6,
      path: `#lander`,
      name: `About`,
    },
    {
      id: 5,
      path: `#switch`,
      name: `Clients`,
    },
    {
      id: 1,
      path: `/`,
      name: `Team`
    },
    {
      id: 1,
      path: `/`,
      name: `Insights`
    },
  ]
</script>

<style>

</style>