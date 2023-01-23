<template>
  <h2>{{customTitle ? 'Entraron' :'Salieron'}}</h2>
  <p>{{ Counter }} <sup>2</sup> = {{ squareCounter }}</p>
  <div>
    <button @click="increse">+1</button>
    <button @click="descrease">-1</button>
  </div>
</template>

<script>
export default {
  props:['title, start'],
  data() {
    return {
      Counter: this.start
    };
  },
  methods: {
    getSquareValue() {
      return this.Counter * this.Counter;
    },

    increse() {
      this.Counter ++;
    },
    descrease() {
     this.Counter --;
    },
  },

  computed: {
    squareCounter() {
      return this.Counter * this.Counter;
    },
    customTitle(){
      console.log(this.title)
      
      return this.title

    },
  },
};
</script>

<style>
button {
  background-color: #64b687;
  border-radius: 5px;
  border: 1px solid white;
  color: white;
  cursor: pointer;
  margin: 0 5px;
  padding: 5px 15px;
  transition: 0.3s ease-in-out;
}

button:hover {
  background-color: #5aaa;
  transition: 0.3s ease-in-out;
}
</style>
