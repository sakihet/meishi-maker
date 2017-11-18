<template lang="pug">
#app
  h1 Meishi Maker
  .grid
    .grid-cell
      MeishiCanvas(
        :leftTopTexts="getLeftTopTexts"
        :backgroundColor="getBgColor"
      )
    .grid-cell.card-params
      input(type="text" v-model="name")
      br
      input(type="text" v-model="job")
      br
      input(type="text" v-model="url")
      br
      input(type="text" v-model="mailaddress")
      br
      input(type="text" v-model="organization")
      br
      input(type="text" v-model="backgroundColor")
</template>

<script>
import MeishiCanvas from './components/atoms/MeishiCanvas'

export default {
  name: 'app',
  components: {
    MeishiCanvas
  },
  data () {
    return {
      name: 'hello, world',
      job: 'job',
      url: 'example.com',
      mailaddress: 'test@example.com',
      organization: 'organization',
      backgroundColor: '#eeeeee'
    }
  },
  computed: {
    getLeftTopTexts: function () {
      return [this.name, this.job, this.url, this.mailaddress, this.organization]
    },
    getBgColor: function () {
      return this.backgroundColor
    }
  },
  methods: {
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.grid {
  display: flex;
  flex-direction: rows;
}
.grid-cell {
  flex: 1;
}
.card-params {
  text-align: left;
}
</style>
