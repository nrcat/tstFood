<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <select v-model="selected">
      <option v-for="food in foodlist" v-bind:key="food.id" >
        {{food.name}}
      </option>
    </select>
    <button v-on:click="randomPick">Randon pick</button>
    <MyMap :huh="selected"/>
  </div>
</template>

<script>
import MyMap from './MyMap'

export default {
  name: 'HelloWorld',
  props: {
    selected: {
      type: String
    }
  },
  components: {
    MyMap
  },
  methods: {
    randomPick: function (event) {
      var randFood
      do {
        randFood = this.foodlist[Math.floor(this.foodlist.length * Math.random())]
      }
      while (this.selected === randFood.name)
      this.selected = randFood.name
    }
  },
  data () {
    return {
      msg: 'Eat Good West',
      foodlist: [
        {
          id: 1,
          name: '牛一',
          location: 'TST',
          count: 0
        },
        {
          id: 2,
          name: '酒鍋',
          location: 'TST',
          count: 0
        },
        {
          id: 3,
          name: 'Gelato-Go',
          location: 'TST',
          count: 0
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
