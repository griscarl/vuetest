<template>
  <div>
    <div v-bind:key="building.id" v-for="building in Buildings" v-bind:is="building.thing">
      <!--v-bind:key="todo.id" v-for="todo in todos">-->

      <Constructor />
    </div>
  </div>
</template>

<script>
  import Constructor from './Constructor'
  export default {
    name: "BuildingList",

    components: {
      Constructor
    },
    data() {
      return {
        Buildings: [
          {
            id: 1,
            thing: Constructor
          },
          {
            id: 2,
            thing: Constructor
          },
          {
            id: 2,
            thing: Constructor
          },
        ]
      }
    }
  }
</script>

<style scoped>
</style>