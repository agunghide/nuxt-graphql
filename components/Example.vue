
<template>
  <div />
</template>

<script>
// import capsulesQuery from '@/query/capsules'
// import capsulesWithVariables from '@/query/capsulesWithVariables'
import capsulesWithSkip from '@/query/capsulesWithSkip'

export default {
  name: 'NuxtExample',
  mounted() {
    this.getData()
  },
  methods: {
    async getData() {
      try {
        await this.$apollo.query({
          query: capsulesWithSkip,
          variables: {
            skipDragon: true
          }
        })
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>
