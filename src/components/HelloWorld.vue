<template>
  <div class="hello" @click="state">
    <img v-if="mouth === true"  src="../assets/CoachO1.png"/>
    <img v-if="mouth === false" src="../assets/CoachO2.png"/>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Geaux Tigers',
      mouth: true,
      num: 1,
      sound: ''
    }
  },
  methods: {
    state () {
      this.mouth = false
      console.log(this.sound)
      var audio = new Audio(require('../assets/Clip4.mp3'))
      audio.play().then(response => {
        this.lips(this.mouth)
      }).catch(e => {
        console.log(e)
      })
    },
    lips () {
      setTimeout(function () {
        console.log('giants', this.mouth)
        this.mouth = false
        console.log('380', this.mouth)
        return this.mouth
      }, 1000)
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
