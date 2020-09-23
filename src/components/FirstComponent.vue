<template>
  <div>
    <h1>Test</h1>
    <h2>Titre 2</h2>
    <p>Propriétés classiques : {{ truc }} // {{ chose }} // {{ phrase}}</p>
    <p>Propriétés calculées : {{ onlyFirstWord }}</p>
    <p>Getter / Setter :
      <ul>
        <li><span v-pre>{{ hello }}</span> {{ hello}}</li>
        <li><span v-pre>{{ world }}</span> {{ world}}</li>
        <li><span v-pre>{{ helloWorld }}</span> {{ helloWorld }}</li>
      </ul>
      <button @click="populateHello">populate hello world</button>
    </p>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      truc: "oui",
      chose: "non",
      phrase: "le chaton est tout mignon",
      hello: "",
      world: ""
    }
  },
  computed: {
    onlyFirstWord: function () {
      return this.phrase.split(' ')[0].toUpperCase();
    },
    helloWorld: {
      get: function () {
        return this.hello + ' ' + this.world
      },
      set: function (newValue) {
        const newHelloWorld = newValue.split(' ')
        this.hello = newHelloWorld[0]
        this.world = newHelloWorld[newHelloWorld.length - 1]
      }
    }
  },
  created() {
    
  },
  mounted() {
    
  },
  methods: {
    populateHello: function () {
      this.helloWorld = 'Hello World'
    }
  }
}
</script>

<style scoped>

</style>