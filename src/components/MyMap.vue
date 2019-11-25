<template>
  <div class="myMap">
    <h1 v-if="this.huh != undefined">Location of {{this.huh}}</h1>
    <div v-if="this.huh != undefined" class="mapouter">
      <div class="gmap_canvas">
        <iframe width="400" height="300" id="gmap_canvas" :src="q" frameborder="0" scrolling="no" marginheight="0" marginwidth="0">
        </iframe>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'myMap',
  props: ['huh'],
  data () {
    return {
      msg: 'TEST'
    }
  },
  computed:{
    q : function () {
      return "https://maps.google.com/maps?q=TST+" + this.huh + "&t=&z=18&ie=UTF8&iwloc=&output=embed"
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
