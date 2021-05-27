<template>
  <div class="wcol-md-6">
    <h3>Child Component 1</h3>
    <p>Ben User.vue isimli Parent Component'in içerisindeki bir Child componentim</p>
    <p> Kullanıcı Adı : {{ name }}</p>
    <p> Kullanıcı Adı Ters Yazımı  : {{ switchName() }} </p>
    <p>Kullanıcı Yaşı : {{ yas }} </p>
    <hr>
    <p> childan parenta veri transferi yapma </p>
    <button @click="parenteVeriTransfer"> Parenta Veri Gönder </button>
    
  </div>
</template>
<script>
  export default{
   
  //props : ["name"],
  //propsa özellik ekleme işlemleri ya da validation işlemleri
  props : {
     name : {
       type : String,
       required :true,
       //default value ayarlanabilir ama required yaptığımız için gerek kalmıyor. 
       //default : "Merhaba "
     },
     yas : {
       type : String
     }
  },
   methods : {
     switchName(){
       return this.name.split("").reverse().join("");
     },
     //Anlamak için  türkçe kullandım isteyen ingilizce kullanabilir
     parenteVeriTransfer(){
       //veriyi göndermek için emmit kullanıyoruz
       //emmit bizim belirlediğimiz kriterlerde veri yaymayı sağlar.key value şeklinde çalışır.
       //this.$emit(key,value)
      //  this.$emit("risalenNurData","Bismillah her hayrın başıdır.")
       this.$emit("childData", "bu veri child componentten geldi")
     }
   },
  }
</script>
<style scoped>
  div {
    background-color: lightcoral;
    padding: 20px;
    border: 1px solid #666;
    display: inline-block;
  }
</style>
