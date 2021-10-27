<script>
export default {
  data () {
    return {
      isSelected: false
    }
  },
  methods: {
    itemClick(event) {
      event.stopPropagation()
      this.isSelected = !this.isSelected
    }
  }
}
</script>