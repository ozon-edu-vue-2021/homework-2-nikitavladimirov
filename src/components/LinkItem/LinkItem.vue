<template>
  <div 
    class="link"
    :class="{ selected:isSelected }" 
    @click="itemClick($event)"
  >
    <i class="fas fa-link"></i>
    <slot></slot>
  </div>
</template>

<script>
import toggleSelect from "../mixins/SelectItemMixin.vue";
export default {
  name: 'LinkItem',
  mixins: [toggleSelect]
}
</script>

<style scoped>
 .link {
   user-select: none;
   padding: 2px 0;
 }
 .link.selected {
   color: orange;
 }
</style>