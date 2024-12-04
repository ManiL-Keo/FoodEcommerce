<template>
  <div class="cart-container">
    <div class="shopping-cart">
      <div class="title">
        <h4><b>Cart</b></h4>
        <div class="items-count">{{ cartItems.length }} items</div>
      </div>
      <hr>
      <div class="cart-items">
        <div class="labels">
          <div class="product-detail-label">Product Detail</div>
          <div class="quantity-label">Quantity</div>
          <div class="price-label">Price</div>
          <div class="total-label">Total</div>
        </div>
        <CartItem
          v-for="(item, index) in cartItems"
          :key="index"
          :item="item"      />
      </div>
      <div class="Continue-Shopping">
        <a href="Home.vue">&leftarrow;</a>
        <span class="text-muted">Continue Shopping</span>
      </div>
    </div>
    <div class="summary-container">
      <Summary :cartItems="cartItems" />
      <CheckoutButton />
    </div>
  </div>
</template>

<script>
import CartItem from '@/components/CartItem.vue';
import Summary from '@/components/Summary.vue';
import CheckoutButton from '@/components/CheckoutButton.vue';

export default {
  components: { CartItem, Summary, CheckoutButton },
  data() {
    return {
      cartItems: [
        { name: 'Banana 1Kg', category: 'Organic Fruit', price: 1.25, toal_price: 44, image: '@/assets/image/p1.jpg', quantity: 1 },
        { name: 'Kiwi 1Kg', category: 'Organic Fruit', price: 4.50, toal_price: 44, image: '@/assets/image/p1.jpg', quantity: 1 },
        { name: 'Orange 1Kg', category: 'Organic Fruit', price: 3.00, toal_price: 44, image: '@/assets/image/p1.jpg', quantity: 1 },
        { name: 'Blueberries 1Kg', category: 'Organic Fruit', price: 6.25, toal_price: 44, image: '@/assets/image/p1.jpg', quantity: 1 },
      ],
    };
  },
  methods: {

  },
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&family=Kanit:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Inter", sans-serif;
}

cart-container{
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  width: 100%;
  height: 100vh;
  padding: 20px;
}
.shopping-cart{
  max-width: 60%;
  width: 100%;
  box-shadow: 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  border-radius: 1rem;
  border: transparent;
  background-color: white;
  color: black;
  padding: 50px;
}

.summary-container{
  max-width: 60%;
  width: 100%;
  
}

hr{
  margin-bottom: 1px;
  border: 0;
  border-top: 1px solid #BFBFBF;
  
}
.title{
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 3rem;
  font-weight: bold;
}

.Continue-Shopping{
  margin-top: 10px;
  margin-bottom: -30px;
}

a {
  color: black;
  font-weight:bolder;
  font-size: 1.7rem;
  margin-right: 10px;
}

span{
  font-size: 1rem;
  cursor: pointer;
  font-weight: bold;
}

.summary-container {
  max-width: 40%;
  width: 100%;
  box-shadow: 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  border-radius: 1rem;
  border: transparent;
  background-color: white;
  padding: 20px;
  color: black;
}

.cart-items {
  max-width: 100%;
  width: 100%;
  background-color: white;
  box-shadow: -6px 0px 6px rgba(0, 0, 0, 0.12), 
              0px 6px 6px rgba(0, 0, 0, 0.12);     
  border-radius: 1rem;
  padding: 20px;
}

.labels {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1fr;
  gap: 10px;
  margin-bottom: 15px;
  font-weight: bold;
  color: #8A8A8A;
}

.labels div {
  text-align: center; 
  font-size: 1.1rem;
}
</style>
