<template>
  <div>
    <div class="products-list">
      <div class="card" v-for="list in products" :key="list.id">
        <img :src="list.image" :alt="list.name">
        <p>가격: {{ list.price }}</p>
        <button @click="addToList(list)">장바구니 추가</button>
      </div>
    </div>
  </div>
</template>

<script setup>
  defineProps({
    products: Array
  });
  const emit = defineEmits(['add-to-cart']);
  const addToList = (list)=>{
    emit('add-to-cart', list);
  };
</script>

<style lang="scss" scoped>
  .products-list{
    display: flex;
    gap: 2rem;
    justify-content: center;
    .card{
      width: 200px;
      text-align: center;
      img{
        width: 100%;
        height: 200px;
        object-fit: cover;
        border-radius: 5px;
      }
    }
  }
</style>