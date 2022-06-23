<template>
    <table id="scrollDemo" v-on:scroll="handleScroll">
      <th>id</th>
      <th>username</th>
      <th>gender</th>
      <tr v-for="n in parseInt(count)" :key="n">
        <td>{{n}}</td>
        <td>atene{{n}}</td>
        <td>male{{n}}</td>
      </tr>
    </table>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
  },
  data() {
    return {
      count: 30
    }
  },
  created () {
    window.addEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll () {
      let height = document.getElementById('scrollDemo').clientHeight;
      if(window.scrollY + window.innerHeight >= height - 200) {
        this.count += 10;
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
