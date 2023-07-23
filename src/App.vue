<script setup>
import { ref, reactive } from 'vue';
const images = reactive([

  {
    thumb: 'https://images.unsplash.com/photo-1682687982046-e5e46906bc6e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxlZGl0b3JpYWwtZmVlZHwzfHx8ZW58MHx8fHx8&auto=format&fit=crop&w=800&q=60',
    full: 'https://images.unsplash.com/photo-1682687982046-e5e46906bc6e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1770&q=80',
  },

  {
    thumb: 'https://images.unsplash.com/photo-1689267305146-155a1459752c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw3fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=800&q=60',
    full: 'https://images.unsplash.com/photo-1689267305146-155a1459752c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2128&q=80',
  },

  {
    thumb: 'https://images.unsplash.com/photo-1646029642262-022158ff5794?ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxlZGl0b3JpYWwtZmVlZHwxNnx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=60',
    full: 'https://images.unsplash.com/photo-1646029642262-022158ff5794?ixlib=rb-4.0.3&ixid=M3wxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
  },

  {
    thumb: 'https://images.unsplash.com/photo-1677080946126-99bbc7b19747?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw0MHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=60',
    full: 'https://images.unsplash.com/photo-1677080946126-99bbc7b19747?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2832&q=80',
  },

  {
    thumb: 'https://images.unsplash.com/photo-1689835775825-b625f67be264?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw5Nnx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=60',
    full: 'https://images.unsplash.com/photo-1689835775825-b625f67be264?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
  },
])

const activeIndex = ref(0)

function next(currentIndex) {
  activeIndex.value = (currentIndex + 1) % images.length;
}

function prev(currentIndex) {
  activeIndex.value = (currentIndex - 1 + images.length) % images.length;
}

</script>

<template>
  <h1 class="text-4xl mb-10 ">Module 4 Assignment</h1>
  <div class="max-w-2xl m-auto  ">
    <div v-for="(image, index) in images" :key="index" class="w-full relative"
      :class="activeIndex == index ? '' : 'hidden'">
      <img class=" rounded-sm w-full " :src="image.full" alt="">

      <div class="flex items-center justify-between w-full  absolute inset-y-0 px-1 ">
        <!-- Previous Button -->
        <div @click="next(index)"
          class=" cursor-pointer flex items-center justify-center bg-white/70 hover:bg-white/90 text-black rounded-full w-10 h-10">
          <p class="text-black" href="">&lt</p>
        </div>
        <!-- Next Button -->
        <div @click="prev(index)"
          class=" cursor-pointer flex items-center justify-center hover:bg-white/90 bg-white/70 text-black rounded-full w-10 h-10">
          <p class="text-black" href="">></p>
        </div>
      </div>
    </div>

  </div>
</template>

<style scoped></style>
