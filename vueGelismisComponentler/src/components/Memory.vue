<template>
  <div>
    <!-- slotlarda isimlerde yaptık -->
    <div class="memory">
      <slot name="baslik"> </slot>
    </div>
    <div class="memory">
      <slot name="heading"> </slot>
    </div>
    <div class="memory">
      <slot> </slot>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
div.memory {
  border: 1px solid #ccc;
  box-shadow: 1px 1px 2px #666;
  padding: 20px 20px;
  margin-top: 20px;
}
</style>
