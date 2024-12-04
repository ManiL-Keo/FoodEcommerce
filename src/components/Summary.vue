<template>
    <div class="summary">
      <h5><b>Order Summary</b></h5>
      <hr />
      <div class="summary-details">
        <div class="row">
          <div class="col">ITEMS {{ totalItems }}</div>
          <div class="text-right col">&dollar;{{ totalPrice }}</div>
        </div>
      </div>
      <form>
        <p>SHIPPING</p>
        <select v-model="selectedShipping">
            <option value="5">Standard Delivery - &dollar;5</option>
            <option value="10">Fast-Delivery- &dollar;10</option>
        </select>
        <p>Payment Option</p>
        <div class="payment">
            <span>cash</span>
            <span>credit card</span>
        </div>
      </form>
      <hr>
      <div class="total-price">
        <div class="row">
          <div class="col">TOTAL COST</div>
          <div class="text-right col">&dollar; {{ (totalPrice + shippingCost).toFixed(2) }}</div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['cartItems'],
    data(){
        return {
            selectedShipping: 5,
        };
    },
    computed: {
      totalItems() {
        return this.cartItems.reduce((sum, item) => sum + item.quantity, 0);
      },
      totalPrice() {
        return this.cartItems.reduce((sum, item) => sum + item.price * item.quantity, 0);
      },
      shippingCost() {
        return this.selectedShipping; 
      },
    },
  };
  </script>
  
  <style scoped>

hr{
  margin-bottom: 15px;
  border: 0;
  border-top: 1px solid #BFBFBF;
}

.summary-details .row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 1.1rem;
  color: black;
  margin-bottom: 10px;
}

.summary-details .row .col,
.summary-details .row .text-right col {
    font-weight: bold;
}

h5{
    font-size: 3rem;
    font-weight: bold;
    margin-bottom: 20px;
}
p{
    font-size: 1.1rem;
    margin-bottom: 15px;
    font-weight: bold;
}

select{
    width: 100%;
    background-color: #ffffff; 
    border: 1px solid #000000; 
    border-radius: 10px;
    font-size: 1rem;
    color: #8A8A8A;
    cursor: pointer;
    padding: 20px;
}

.select option {
  padding: 40px;
  font-size: 1rem;
  color: #ffffff;
  background-color: #fff;
}


.text-right {
  text-align: right;
}

.payment{
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin-bottom: 100px;
}

.total-price .row{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 40px;
}
</style>
  