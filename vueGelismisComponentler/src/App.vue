<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6 col-md-offset-3">
        <br />
        <br />
        <button
          @click="selectedComponent = 'appMemory'"
          class="btn-sm btn btn-primary"
        >
          appMemory
        </button>
        <button
          @click="selectedComponent = 'appNewMemory'"
          class="btn-sm btn btn-primary"
        >
          appNewMemory
        </button>
        <button
          @click="selectedComponent = 'appAuthor'"
          class="btn-sm btn btn-primary"
        >
          Author
        </button>
        <button
          @click="selectedComponent = 'appTest'"
          class="btn-sm btn btn-primary"
        >
          Test
        </button>
        <p>{{ selectedComponent }}</p>
        <keep-alive>
          <component :is="selectedComponent">
            <h1 slot="baslik">Slot Kullanımı</h1>
            <h5 slot="heading">hello world...</h5>
          </component>
        </keep-alive>
        <!-- slotlarda isimlendirme yaptık  -->
        <!-- <app-memory>
           <h1 slot="baslik">  Slot Kullanımı </h1>
          <h5 slot="heading"> hello world...  </h5>
        </app-memory> -->
      </div>
    </div>
  </div>
</template>
<script>
import Memory from "./components/Memory";
import NewMemory from "./components/NewMemory";
import Author from "./components/Author";
import Test from "./components/Test";
export default {
  data: function () {
    return {
      selectedComponent: "appMemory",
    };
    //seçili component
  },
  components: {
    appMemory: Memory,
    appNewMemory: NewMemory,
    appAuthor: Author,
    appTest: Test,
  },
};
</script>
