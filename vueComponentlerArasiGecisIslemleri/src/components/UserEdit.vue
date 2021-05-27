<template>
  <div class="col-md-s6">
    <h3>Child Component 2</h3>
    <p>Ben User.vue isimli Parent Component'in içerisindeki bir diğer Child componentim</p>
    <p>Kullanıcı Yaşı :   {{yas}} </p>
    <button @click="yasDegistir">Yaş Bilgisi Değiştir</button>
  </div>
</template>
<script>
export default{
  props :  ["yas"],

  methods : {
    yasDegistir(){
       this.yas= "30"
       this.$emit("yasDegistir",this.yas)
    }
  }
}
</script>

<style scoped>
  div {
    background-color: lightgoldenrodyellow;
    padding: 20px;
    border: 1px solid #666;
    display: inline-block;
  }
</style>

