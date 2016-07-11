<template>
  <div class="modal-container" v-if="isOpen">
    <section
      class="modal-wrapper"
      :style="{
        background: styles.backgroundColor,
        padding: styles.padding, 
        borderRadius: styles.borderRadius
      }">
      <slot></slot>
    </section>
    <section
      class="modal-overlay"
      @click="onClickOverlay"
      :style="{ background: styles.overlayBackgroundColor }">
    </section>
  </div>
</template>

<script scoped>
export default {
  methods: {
    destroyModal() {
      this.$destroy(true)
    },
    onClickOverlay() {
      if(this.shouldCloseOnOverlayClick) this.destroyModal()
    },
  },

  computed: {
    styles() {
      const defaults = {
        backgroundColor: '#fff',
        padding: '20px',
        borderRadius: '2px',
        overlayBackgroundColor: 'rgba(0, 0, 0, 0.3)',
      }

      return Object.assign(defaults, this.customStyle)
    },
  },

  ready() {
    if (this.closeTimeoutMS <= 0) return
    setTimeout(this.destroyModal.bind(this), this.closeTimeoutMS)
  },
  destroyed() {
    this.onRequestClose()
  },

  props: {
    isOpen: {
      type: Boolean,
      default: false,
    },

    onRequestClose: {
      type: Function,
      default() {},
    },

    closeTimeoutMS: {
      type: Number,
      default: -1000,
    },

    shouldCloseOnOverlayClick: {
      type: Boolean,
      default: false,
    },

    customStyle: {
      type: Object,
      // default() {
      //   return {
      //     backgroundColor: '#fff',
      //     padding: '20px',
      //     borderRadius: '2px',
      //     overlayBackgroundColor: 'rgba(0, 0, 0, 0.3)',
      //   }
      // },
    },
  },
}  
</script>

<style>
.modal-wrapper {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%);

  z-index: 9999;
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.30);

  z-index: 9998;
}
</style>