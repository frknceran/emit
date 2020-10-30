<template>
  <div id="app">
    <div class="row mb-5">
      <div class="col-12">
        <h4>Parent</h4>
        <table class="table">
          <tr class="p-2">
            <td><p>Value with object as prop (reference) of parent:</p></td>
            <td>{{ valueReference }}</td>
          </tr>
          <tr class="p-2">
            <td><p>Value with emit of parent:</p></td>
            <td>{{ valueEmit }}</td>
          </tr>
        </table>
      </div>
    </div>
    <div class="row">
      <div class="col-6">
        <ChildReference 
          :valueReference="valueReference"
          :test="test"
        >
        </ChildReference>
      </div>

      <div class="col-6">
        <ChildEmit 
          :initialValue = "valueEmit" 
          @update-value-by-child="updateParentValue">
        </ChildEmit>
      </div>
    </div>
  </div>
</template>

<script>
import ChildReference from "./components/ChildReference.vue"
import ChildEmit from "./components/ChildEmit.vue"

export default {
  name: 'App',
  components: {
    ChildReference,
    ChildEmit
  },

  data () {
    return {
      valueReference : {},
      valueEmit: {},
      test: "furkan"
    }
  },

  methods: {
    updateParentValue(newValue) {
      console.log("new Value", newValue)
      this.valueEmit = newValue
    }
  },
}
</script>

<style>
#app {
   font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
