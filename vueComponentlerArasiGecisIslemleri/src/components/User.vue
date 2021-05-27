<template>
  <div class="container">
    <h1>Parent Component (User)</h1>
    <p>Burası parent component yani herşeyin import edildiği component :)</p>
    <input v-model="title">
    <button @click="changeName">Adını Değiştir</button>
    <p>Child componentinden gelen data : {{childData}} </p>
    <p> child componentten değişen yaş bilgisi  : {{ yas }} </p>
    <hr />
    <div class="row">
      <app-user-detail :yas="yas" @childData="childData=$event" v-bind:name="title"></app-user-detail>
      <app-user-edit @yasDegistir="yas = $event"  :yas="yas"></app-user-edit>
    </div>
  </div>
</template>
<script>
import UserDetail from "./UserDetail";
import UserEdit from "./UserEdit";
export default {
  components: {
    appUserDetail: UserDetail,
    appUserEdit: UserEdit,
  },

  data:function(){
   return {
     title     : "Cemşit",
     childData : "",
     yas : 25

   }
  },
  methods : {
    changeName(){
     this.title= "Çetin"
    }
  }
};
</script>

<style>
div.container {
  margin-top: 30px;
  padding: 20px 40px;
  background-color: #6a8d99;
  border: 1px solid #666;
}
div.row {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
