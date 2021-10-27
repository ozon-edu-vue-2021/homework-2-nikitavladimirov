<template>
  <div>
    <dir-item
      :treeData='dataJSON.contents'
    >
      {{ dataJSON.name }}
    </dir-item>
  </div>
</template>

<script>
import JSON from "../../public/static/node_modules.json"
import DirItem from "./DirItem/DirItem.vue"
export default {
  components: {DirItem},
  name: 'DirectoryTree',
  data: () => {
    return {
      dataJSON: JSON
    }
  },
}
</script>