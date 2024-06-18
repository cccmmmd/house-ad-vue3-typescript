<script lang="ts">
import { defineComponent, ref } from 'vue';
import House from './types/House'
import HouseList from './components/HouseList.vue';
import Order from './types/Order';


export default defineComponent({
  name: 'App',
  components:{ HouseList},
  setup() {
    const houses = ref<House[]>([
      { name: 'Exquisite room',
        sqare: 20,
        id: 'A01',
        region: 'North',
        price: 760
      },
      { name: 'Junior Suite',
        sqare: 10,
        id: 'M03',
        region: 'South',
        price: 600
      },
      { name: 'Family House',
        sqare: 55,
        id: 'A06',
        region: 'North',
        price: 900
      },
      { name: 'Double room',
        sqare: 25,
        id: 'A13',
        region: 'West',
        price: 700
      },
      { name: 'Triple room',
        sqare: 35,
        id: 'C20',
        region: 'South',
        price: 800
      },
      { name: 'Quadruple room',
        sqare: 50,
        id: 'N12',
        region: 'West',
        price: 1000
      },
    ])

    const order = ref<Order>('price')
    const clickHandler = (term: Order) => {
      order.value = term
    }
    return { houses, clickHandler, order }
  },
})
</script>

<template>
	<div class="app">
    <header>
      <div class="order">
        <button @click="clickHandler('price')">Order by price</button>
		    <button @click="clickHandler('sqare')">Order by sqare</button>
		    <button @click="clickHandler('region')">Order by region</button>
      </div>
    </header>
				<HouseList :houses="houses" :order="order" />
	</div>
</template>

<style scoped>
 header {
    text-align: center;
  }
  header .order {
    margin-top: 20px;
  }
  button {
    margin: 0 10px;
    color: #1195c9;
    border: 3px solid #1195c9;
    background: #d5f0ff;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
  }
</style>
