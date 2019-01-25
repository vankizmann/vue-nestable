<template>
  <ComponentExample link="Simple">
    <VueNestable v-model="nestableItems">
      <VueNestableHandle
        slot-scope="{ item }"
        :item="item"
      >
        <a
          href="javascript:void(0)"
          @click="item.collapsed = !item.collapsed"
        >
          [+]
        </a>
        <i class="fas fa-user" />
        {{ item.text }}
      </VueNestableHandle>
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
          collapsed: true,
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
