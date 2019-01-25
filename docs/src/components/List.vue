<template>
  <ComponentExample link="List">
    <VueNestable v-model="nestableItems">
      <span slot-scope="{ item, index }">
        <a
          href="javascript:void(0)"
          @click="item.collapsed = !item.collapsed"
        >
          [+]
        </a>
        <small>[{{ index }}]</small> {{ item.text }}
      </span>
    </VueNestable>
  </ComponentExample>
</template>

<script>
import ComponentExample from './ComponentExample.vue'

export default {
  components: {
    ComponentExample
  },

  data () {
    return {
      nestableItems: [
        {
          id: 0,
          text: 'Andy',
          collapsed: true
        }, {
          id: 1,
          text: 'Harry',
          collapsed: false,
          children: [{
            id: 2,
            text: 'David'
          }]
        }, {
          id: 3,
          text: 'Lisa',
          collapsed: true
        }
      ]
    }
  }
}
</script>

<style scoped>
</style>
