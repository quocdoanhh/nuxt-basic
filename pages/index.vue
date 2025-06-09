<script setup lang="ts">
import userImage from "@/assets/images/user.png";
import defaultImage from "@/public/images/default.png";
const { $hello } = useNuxtApp();

definePageMeta({
  middleware: "auth",
});

const counter = useCounter();
const store = useCounterStore();
console.log(store);
</script>

<template>
  <div class="Main">
    <Profile />
    <img :src="userImage" alt="User Image" srcset="" />
    <img :src="defaultImage" alt="Defaul Image" srcset="" />
    <IconBell />
    {{ $hello("world") }}
    <div>
      Counter: {{ counter }}
      <button @click="counter++">+</button>
      <button @click="counter--">-</button>
    </div>
  </div>
</template>
