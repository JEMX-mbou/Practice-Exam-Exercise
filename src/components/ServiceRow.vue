<template>
  <section id="service" class="py-10">
    <div class="container">
      <div class="row jc-center">
        <div class="col-m-12 col-l-8 text-center pb-5" id="service-intro">
          <h2>{{ service.data.title }}</h2>
          <p>{{ service.data.intro }}</p>
        </div>
      </div>
      <div class="row ai-stretch">
        <service-block v-for="service in service.data.services" :data="service" :key="service.id" />
      </div>
    </div>
  </section>
</template>

<script setup>
import axios from 'axios'
import { onMounted, reactive } from 'vue'

import ServiceBlock from './ServiceBlock.vue'

const url = 'http://jemx.nl/FTED/ExOp/'

const service = reactive({ data: {} })

onMounted(() => {
  axios
    .get(url)
    .then((data) => {
      service.data = data.data.service
    })
    .catch(() => {
      console.log('something went wrong!')
    })
})
</script>

<style lang="scss" scoped>
#service {
  background: linear-gradient(0deg, rgba(34, 34, 34, 1) 0%, rgba(68, 68, 68, 1) 100%);
}
</style>
