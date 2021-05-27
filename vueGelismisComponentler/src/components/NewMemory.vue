<template>
  <div>
      <h1> NewMemory componenti</h1>
      <button @click="counter++">Arttır</button>
      <p> {{counter}} </p>
  </div>
</template>
<script>
export default{
    data(){
        return{
           counter : 0
        }
    },
    destroyed(){
      console.log("destroyed");
    },
    activated(){
      console.log("activated");
    },
    deactivated(){
      console.log("deactivated");
    }
}
</script>