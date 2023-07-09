<template>
  <div id="app">
    <VirtualList
      class="list"
      :data-key="'id'"
      :data-sources="items"
      :data-component="Item"
      :estimate-size="30"
      item-class="list-item-fixed"
      :keeps="60"
    >
      <!-- <div slot="header" class="header-m">header</div>
      <div slot="footer" class="loading-spinner-m">Loading ...</div> -->
    </VirtualList>
  </div>
</template>

<script setup>
  import { ref } from 'vue'
  import VirtualList from 'vue-virtual-scroll-list'

  import Item from './Item.vue'

  const TOTAL_COUNT = 10000

  const DataItems = []
  let count = TOTAL_COUNT
  while (count--) {
    const index = TOTAL_COUNT - count
    DataItems.push({
      index,
      name: index + '-name',
      id: index
    })
  }

  const items = ref(DataItems)
</script>

<style>
  .header-m {
    height: 100px;
    background-color: pink;
  }
  .loading-spinner-m {
    height: 50px;
  }
  .list {
    width: 100%;
    height: 500px;
    border: 2px solid;
    border-radius: 3px;
    overflow-y: auto;
    border-color: dimgray;
  }

  .list .list-item-fixed {
    display: flex;
    align-items: center;
    padding: 0 1em;
    height: 30px;
    border-bottom: 1px solid;
    border-color: lightgray;
  }
</style>
