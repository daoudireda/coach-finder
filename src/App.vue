<template>
  <header-view></header-view>
  <router-view v-slot="slotProps">
    <transition name="route" mode="out-in">
      <component :is="slotProps.Component"></component>
    </transition>
  </router-view>
</template>

<script>
import Header from './components/layout/Header.vue';

export default {
  components: {
    'header-view': Header,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}

.router-enter-from {
  opacity: 0;
  transform: translateY(20px);
}

.router-enter-to {
  opacity: 1;
  transform: translateY(0);
}

.router-enter-active {
  transition: opacity 0.3s, transform 0.3s;
}

.router-leave-from {
  opacity: 1;
  transform: translateY(0);
}
</style>
