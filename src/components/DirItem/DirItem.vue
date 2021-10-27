<template>
  <ul 
    class="item-wrapper directory" 
    :class="{expanded: isExpanded}"
    @click="directoryClick($event)"
  >
    <span>
      <i v-if="isExpanded" class="fas fa-folder-open"></i>
      <i v-else class="fas fa-folder"></i>
      <slot></slot>
    </span>

    <li v-if="isExpanded">
        <component 
          v-for="(item, i) in treeData"
          :key="`${item.name}-${i}`" 
          :is="checkType(item)"
          :treeData="item.contents"
        >
          {{ item.name }}
        </component>
    </li>
  </ul>
</template>

<script>
import FileItem from "../FileItem/FileItem.vue";
import DirItem from "../DirItem/DirItem.vue";
import LinkItem from "../LinkItem/LinkItem.vue"
export default {
  name: 'DirItem',
  components: {
    DirItem,
    FileItem, 
    LinkItem
  },
  props: {
    treeData: {
      type: Array,
      default: () => []
    }
  },
  data () {
    return {
      isExpanded: false
    }
  },
  methods: {
    checkType(item) {
      switch (item.type) {
        case 'file': return 'file-item';
        case 'directory': return 'dir-item';
        case 'link': return 'link-item';
      }
    },
    directoryClick (event) {
      event.stopPropagation()
      this.isExpanded = !this.isExpanded
    }
  }
}
</script>

<style scoped>
.directory {
  padding: 2px 0;
}
ul {
  padding-left: 0 ;
}
ul > span {
  user-select: none;
}
li { 
  padding-left: 10px;
}
ul:hover, li:hover {
  cursor: pointer;
}
</style>