<template>
  <div class="home">
    <button @click="bounce = !bounce">Bounce</button><br>
    <section>
      <transition name="bounce_ani">
        <img v-if="bounce" alt="Vue logo" src="../assets/logo.png">
      </transition>
    </section>
    <button @click="roll = !roll">Roll</button><br>
    <section>
      <transition name="roll_ani">
        <img v-if="roll" alt="Vue logo" src="../assets/logo.png">
      </transition>
    </section>
    <button @click="animated = !animated">Animate</button><br>
    <section>
      <transition name="animate" enter-active-class="animated flipInY" leave-active-class="animated zoomOutRight">
        <img v-if="animated" alt="Vue logo" src="../assets/logo.png">
      </transition>
    </section>
  </div>
</template>

<script>

export default {
  name: 'Home',
  data () {
    return {
      bounce: false,
      roll: false,
      animated: false
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

.roll_ani-enter-active {
  animation: roll-in .5s;
}
.roll_ani-leave-active {
  animation: roll-in .5s reverse;
}
@keyframes roll-in {
  0% {
    transform: scale(0) rotateZ(0deg) translateX(-250px);
    opacity: 0;
  }
  25% {
    opacity: 1;
  }
  100% {
    transform: scale(1) rotateZ(360deg) translateX(0px);
    opacity: 1;
  }
}
</style>
