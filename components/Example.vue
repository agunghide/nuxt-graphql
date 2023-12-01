<!-- Please remove this file from your project -->
<template>
  <code>
    {{
      JSON.stringify(response)
    }}
  </code>
</template>

<script>
import capsulesQuery from '@/query/capsules'

export default {
  name: 'NuxtExample',
  data() {
    return {
      response: null
    }
  },
  mounted() {
    this.getData()
  },
  methods: {
    async getData() {
      try {
        this.response = await this.$apollo.query({
          query: capsulesQuery
        })
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>
