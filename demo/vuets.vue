<template>
  <div>
    <button v-on:click="decrement">-</button>
    {{ count }}
    <button v-on:click="increment">+</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { Vue, Component, Prop } from 'vue-property-decorator'


// Define the component in class-style
@Component
export default class Counter extends Vue {
  // Class properties will be component data
  count = 0
  @Prop(Number) readonly propA: number | undefined
  @Prop({ default: 'default value' }) readonly propB!: string
  @Prop([String, Boolean]) readonly propC: string | boolean | undefined

  // Methods will be component methods
  increment() {
    this.count++
  }

  decrement() {
    this.count--
  }
  test(): number{
    return 2;
  }
}
</script>
