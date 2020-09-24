<template>
  <div class="container">
    <today></today>
    <nuxt-link to="add">
      <div class="fab">
        <a-icon type="plus" />
      </div>
    </nuxt-link>
  </div>
</template>

<script>

import Today from '~/components/today'
export default {
  components: { Today },
  methods: {}
}
</script>

<style>
.container {
  padding: 0.5rem;
}

.fab {
  background: #7BAE7F;
  border-radius: 50%;
  color: white;
  position: fixed;
  right: 1.5rem;
  bottom: 1.5rem;
  font-size: 30px;
  z-index: 900;
  text-align: center;
  height: 50px;
  width: 50px;
  padding-top: 2px;
  cursor: pointer;
}
</style>
