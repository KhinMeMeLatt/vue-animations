<template>
  <div class="home">
    <section>
      <button @click="bounce = !bounce">Bounce</button><br>
      <transition name="bounce_ani">
        <img v-if="bounce" alt="Vue logo" src="../assets/logo.png">
      </transition>
    </section>
  </div>
</template>

<script>

export default {
  name: 'Home',
  data () {
    return {
      bounce: false
    }
  }
}
</script>

<style scoped>
section {
  min-height: 200px;
}
.bounce_ani-enter-active {
  animation: bounce-in .5s;
}
.bounce_ani-leave-active {
  animation: bounce-in .5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
</style>
