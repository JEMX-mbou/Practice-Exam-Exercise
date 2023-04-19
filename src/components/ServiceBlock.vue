<template>
  <div class="col-s-12 col-m-6 col-l-4">
    <div
      class="inner service-block fw-nowrap ai-center text-center"
      :id="`service-${service.data.id}`"
    >
      <img :src="`./src/assets/icons/${service.data.icon}`" :alt="service.data.title" />
      <h3>{{ service.data.title }}</h3>
      <p>{{ service.data.description }}</p>
    </div>
  </div>
</template>

<script setup>
const service = defineProps({
  data: Object
})
</script>

<style lang="scss" scoped>
.service-block {
  height: 100%;
  background-color: #fff;
  border-radius: 1rem;
  border-bottom: 0.5rem solid #e74c3c;
  color: #222;

  img {
    width: 4rem;
  }

  h3 {
    position: relative;
    &::after {
      content: '';
      position: absolute;
      top: calc(100% - 0.3em);
      left: 0;
      width: 100%;
      height: 0.2rem;
      background-color: #e74c3c;
    }
  }
}
</style>
