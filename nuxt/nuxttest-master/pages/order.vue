<template>
  <div>
    <div class="back">
      <Back />
    </div>
    <h1 class="name"><strong>Split</strong> order</h1>
    <div class="menu">
      <Menu :items="items" />
    </div>
    <div class="user-order">
      <ul class="orders-list">
        <li
          v-for="(order, index) in orders"
          :key="order.name"
          class="orders-item"
        >
          <Order v-bind="order" :white="index > 0" />
        </li>
        <li class="orders-item"><Profile /></li>
      </ul>
      <div class="place-order">
        <PlaceOrder :full="full" text="Set reminder" @click="full = !full" />
      </div>
    </div>
  </div>
</template>

<script>
import Menu from '~/components/Menu'
import Order from '~/components/Order'
import PlaceOrder from '~/components/PlaceOrder'
import Profile from '~/components/Profile'
import Back from '~/components/Back'

export default {
  layout: 'orderfood',
  components: { Back, Menu, Order, PlaceOrder, Profile },
  data: () => ({
    items: [
      {
        id: 1,
        image: '/images/burger.png',
        amount: 1,
        name: 'Le Pigeon Burger',
        price: '$9.50'
      },

      {
        id: 2,
        image: '',
        amount: 1,
        name: 'Roasted Potato Salad',
        price: '$15.00'
      },

      {
        id: 3,
        image: '/images/croissant.png',
        amount: 1,
        name: 'Croissant',
        price: '$7.50'
      },

      {
        id: 4,
        image: '/images/burrito.png',
        amount: 1,
        name: 'Hot Cheese Burrito',
        price: '$8.00'
      }
    ],
    orders: [
      {
        avatar: '#',
        name: 'You',
        price: '$555',
        photos: ['/images/croissant.png', '/images/burrito.png']
      },
      {
        avatar: '#',
        name: 'Tom',
        price: '$555',
        photos: ['/images/potato.png']
      }
    ],
    full: false
  }),

  head: {
    title: 'Our page'
  }
}
</script>

<style scoped>
.back {
  padding: 2em;
}

.name {
  font-weight: normal;
  padding: 0 1.2em;
}

.orders-item {
  display: inline-block;
  vertical-align: top;
  margin: 0 5%;
  width: 20%;
}

.orders-item:last-child {
  margin-right: 0;
}

.orders-list {
  padding: 0;
  margin: 0;
  text-align: right;
  padding: 2em 0;
}

.menu {
  padding: 1em;
  font-size: 0.7em;
}

.user-order {
  position: relative;
}

.place-order {
  position: absolute;
  right: 0;
  bottom: 0;
  padding: 2em 0;
}
</style>
