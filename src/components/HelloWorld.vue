<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <a href="http://www.google.com">go to google</a>
    <select >
      <option v-for="food in foodlist" v-bind:key="food.id" >
        {{food.name}}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'TEST',
      foodlist: [
        {
          id: 1,
          name: '牛一',
          map: 'test',
          count: 0
        },
        {
          id: 2,
          name: '酒鍋',
          map: 'test',
          count: 0
        },
        {
          id: 3,
          name: 'c',
          map: 'test',
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
