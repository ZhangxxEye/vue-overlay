<template>
    <transition name="fade">
        <div v-show="value" class="vue-overlay"  @touchmove="move" @touchend="handleClick" :style="{zIndex: zIndex}">
        </div>
    </transition>
</template>

<script>
    export default {
      name: "vue-overlay",
      props: {
        zIndex: Number,
        value: {
          type: Boolean,
          default: false
        }
      },
      methods: {
        move (e) {
          e.preventDefault();
          e.stopPropagation();
        },
        handleClick () {
          this.$emit('input', false);
        }
      }
    }
</script>

<style scoped lang="less">
.vue-overlay{
    background: rgba(0, 0, 0, 0.6);
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1000;
}
.fade-enter-active, .fade-leave-active {
    transition: opacity .5s;
}
.fade-enter, .fade-leave-to{
    opacity: 0;
}
</style>