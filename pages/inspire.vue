<template>
  <v-row>
    <v-col class="text-center">
      <p v-for="(v, k) in testAxios" :key="v">
        {{ k }}: {{ v }}
      </p>
    </v-col>
  </v-row>
</template>


<script>
export default {
  name: "inspire",
  data() {
    return {
      testAxios: null,
    };
  },
  methods: {
    async axiosTest() {
      this.testAxios = await this.$axios.$get('todos/1')
    }
  },
  mounted() {
    this.axiosTest()
  }
}
</script>
