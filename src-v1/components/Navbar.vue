<template>
  <nav>
    <h1>버거킹</h1>
    <ul>
      <!-- <li>전체</li>
      <li>Best</li>
      <li>New</li>
      <li>세트메뉴</li>
      <li>음료</li>
      <li>디저트</li> -->
      <li v-for="(list,idx) in categories" :key="idx" @click="selectedClick(list)">{{ list }}</li>
    </ul>
  </nav>
</template>

<script setup>
defineProps({
  categories: Array
})
// import { categories } from '../assets/products';
const emit = defineEmits(['selected']);
const selectedClick = (list)=>{
  emit('selected', list);
};
</script>

<style lang="scss" scoped>
  nav{
    display: flex;
    justify-content: space-between;
    padding: 2rem 5rem;
    ul{
      display: flex;
      gap: 3rem;
      align-items: center;
      li{
        cursor: pointer;
        &:hover{
          font-weight: bolder;
          color: red;
        }
      }
    }
  }
</style>