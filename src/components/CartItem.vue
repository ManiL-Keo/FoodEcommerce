<template>
    <div class="cart-item">
      <div class="item-image">
        <img :src="item.image" :alt="item.name" />
      </div>
      <div class="item-details">
        <div class="item-category">{{ item.category }}</div>
        <div class="item-name">{{ item.name }}</div>
      </div>
      <div class="item-quantity">
        <a href="#" @click.prevent="updateQuantity(-1)">-</a>
        <a href="#" class="border">{{ item.quantity }}</a>
        <a href="#" @click.prevent="updateQuantity(1)">+</a>
      </div>
      <div class="item-price">
        &dollar; {{ item.price.toFixed(2) }}
      </div>
      <div class="item-total_price">
        &dollar; {{ (item.price * item.quantity).toFixed(2) }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['item'],
    methods: {
      updateQuantity(amount) {
        const newQuantity = this.item.quantity + amount;
        if (newQuantity > 0) {
          this.item.quantity = newQuantity;
        }
      },
    },
  };
  </script>
  
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&family=Kanit:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&family=Kanit:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Pacifico&display=swap');
.cart-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  border-bottom: 1px solid #ddd;
  margin-bottom: 1rem;
  background-color: #fff;
  border-radius: 20px;
  border: 1px solid #47B749;
  font-family: "Inter", sans-serif;
  box-shadow: 0 6px 4px rgba(0, 0, 0, 0.1);
}

.item-image img {
  width: 60px;
  height: 60px;
  object-fit: cover;
  border-radius: 4px;
}

.item-details {
  flex: 2; 
  margin-left: 1rem;
}

.item-category {
  font-size: 1.5rem;
  color: #000000;
  font-weight: bold;
  font-family: "Pacifico", cursive;
}

.item-name {
  font-size: 1rem;
  font-weight: 400;
  margin-top: 4px;
  color: #000000;
}

.item-quantity,
.item-price,
.item-total_price {
  display: flex;
  justify-content: center; 
  align-items: center;
  flex: 1; 
}
.item-quantity {
  justify-content: flex-start; 
}

.item-price {
  justify-content: center; 
}

.item-total_price {
  justify-content: flex-end; 
}

.item-quantity a {
  color: black;
  font-size: 1.2rem;
  font-weight: bold;
}

.border {
  border: 1px solid #000000;
  padding: 1px 2px;
  min-width: 2rem;
  text-align: center;
}

.btn-quantity {
  font-size: 1.2rem;
  cursor: pointer;
  padding: 0.5rem;
  border-radius: 4px;
  text-decoration: none;
  color: #333;
  margin: 0 5px;
  transition: background-color 0.3s;
}

.btn-quantity:hover {
  background-color: #ddd;
}

.item-price,
.item-total_price {
  font-size: 1.2rem;
  font-weight: bold;
  color: #333;
}

</style>
  