<script>
export default {

    data(){
    return {
      counter: 2,
      name: ''
    }
  },
  methods:{
    add(){
      this.counter++
    },
    reduce(){
      this.counter--
    },
    setName(event, lastName){
      this.name = event.target.value + ' ' + lastName;
    }
  }
}
</script>

<template>
   <div id="handler">
      <h2>Events Example</h2>
      <!-- Event handler with v-on and onclick -->
      <button @click="add">Add</button>
      <!-- Event handler with v-on and onclick -->

      <button @click="reduce">Reduce</button>
      <p>Result: {{ counter }}</p>
      <!-- Gets value once, after that no changes can be done with v-once -->
      <p v-once>Result that only appears once: {{ counter }}</p>
      <!-- Event handler with v-on and input -->
      <!-- We use one argument to work with -->
      <input type="text" v-on:input="setName($event, 'Carlsson')">
      <!-- We use more than one arguments to work with, then we need to use ($event, and second argument here) -->
<!--       <input type="text" v-on:input="setName($event, 'Carlsson')">
 -->      <p>Your Name: {{ name }}</p>
    </div>
</template>

<style>

#handler {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#handler h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #254034;
  margin: 0 0 1rem 0;
}

#handler p {
  font-size: 1.25rem;
  font-weight: bold;
  border: 1px solid #254034;
  background-color: #254034;
  color: white;
  padding: 0.5rem;
  border-radius: 25px;
  margin-top:4vh
}

#handler input {
  font: inherit;
  border: 1px solid black;
  margin-top:4vh;

}

#handler input:focus {
  outline: none;
  border-color: #1b995e;
  background-color: #d7fdeb;
}

#handler button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #254034;
  background-color: #254034;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
  border-radius: 20px;
  margin: 0 1rem;
}

#handler button:hover,
#handler button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}

.counter {
  font-size: 0.8rem;
  padding-left: 10px;
  padding-right: 10px;
}

</style>