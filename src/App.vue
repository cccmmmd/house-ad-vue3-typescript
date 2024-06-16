<script lang="ts">
import { defineComponent, ref } from 'vue';
import House from './types/House'
import HouseList from './components/HouseList.vue';


export default defineComponent({
  name: 'App',
  components:{ HouseList},
  setup() {
    const houses = ref<House[]>([
      { name: 'Exquisite room',
        square: 20,
        id: 'A01',
        region: 'North',
        price: 660
      },
      { name: 'Junior Suite',
        square: 10,
        id: 'M03',
        region: 'South',
        price: 600
      },
      { name: 'Family House',
        square: 55,
        id: 'A06',
        region: 'North',
        price: 900
      },
      { name: 'Double room',
        square: 25,
        id: 'A13',
        region: 'West',
        price: 700
      },
      { name: 'Triple room',
        square: 35,
        id: 'C20',
        region: 'South',
        price: 800
      },
      { name: 'Quadruple room',
        square: 60,
        id: 'N12',
        region: 'West',
        price: 1000
      },
    ])
    return { houses }
  },
  
})
</script>

<template>
  <div class="app">
    <HouseList :houses="houses"/>
  </div>
</template>

<style scoped>

</style>
