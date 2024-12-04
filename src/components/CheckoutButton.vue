<template>
    <div class="checkout">
      <button class="btn" @click="checkout">CHECKOUT</button>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      checkout() {
        alert('Proceeding to checkout!');
      },
    },
  };
  </script>
  
  <style scoped>
  .checkout{
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .btn {
  border: 1px solid #47B749; 
  background-color: #47B749; 
  color: white; 
  padding: 10px 240px;
  font-size: 1.2rem;
  font-weight: bold;
  border-radius: 15px;
  cursor: pointer;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.btn:hover {
  background-color: #3b9e3b; 
  color: white; 
}
</style>
  