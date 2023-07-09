<template>
  <div class="item-inner">
    <span># {{ source.index }}</span>
    <span>{{ source.name }}</span>
  </div>
</template>

<script>
  export default {
    name: 'fix-size-item',

    props: {
      source: {
        type: Object,
        default() {
          return {}
        }
      }
    },
    created() {
      let t = Date.now()

      while (Date.now() - t < 10) {}
    }
  }
</script>

<style scoped>
  .item-inner span:first-child {
    margin-right: 1em;
  }
</style>
