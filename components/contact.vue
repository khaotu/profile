<template>
  <b-container>
    <b-row align-h="center" class="mb-4">
      <h1>{{ title }}</h1>
    </b-row>
    <b-row  align-v="center" align-h="center" >
      <b-img
        v-for="(i,n) in contacts"
        :key="n"
        class="mx-4"
        rounded="circle"
        sizes="200"
        width="50"
        :src="i.logo"
        @click="toEndpoint(i)">
      </b-img>
    </b-row>
  </b-container>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    contacts: {
      type: Array,
      required: true
    }
  },

  methods: {
    toEndpoint(endpoint) {
      if(endpoint.contact) {
        window.open(endpoint.contact, '_blank');
      }
    }
  }
}
</script>