<template>
  <div 
    class="file"
    :class="{ selected:isSelected }" 
    @click="itemClick($event)"
  > 
    <i class="far fa-file"></i>
    <slot></slot>
  </div>
</template>

<script>
import toggleSelect from "../mixins/SelectItemMixin.vue";
export default {
  name: 'FileItem',
  mixins: [toggleSelect]
}
</script>

<style scoped>
 .file {
   user-select: none;
   padding: 2px 0;
 }
 .file.selected {
   color: red;
 }
</style>