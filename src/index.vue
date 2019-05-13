<template>
    <div class="vue-overlay"  @touchmove="move" @touchend="handleClick" :style="{zIndex: zIndex}">
    </div>
</template>

<script>
    export default {
      name: "vue-overlay",
      props: {
        zIndex: Number
      },
      methods: {
        move (e) {
          e.preventDefault();
          e.stopPropagation();
        },
        handleClick () {
          this.$emit('click');
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
</style>