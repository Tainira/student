<template>
  <div>
    <h1 class="name"><strong>Split</strong> order</h1>
    <Menu :items="items" />
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

export default {
  layout: 'orderfood',
  components: { Menu, Order, PlaceOrder, Profile },
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
.name {
  font-weight: normal;
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
}

.user-order {
  position: relative;
}

.place-order {
  position: absolute;
  right: 0;
  bottom: 0;
}
</style>
