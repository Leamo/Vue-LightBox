<template>
    <div class="lightbox" v-if="image" @click="close">
        <transition name="lightbox-fade">
            <lightbox-pic :image="image" :key="image"></lightbox-pic>
        </transition>
        <div class="lightbox__close" @click="close"><v-icon name="times"/></div>
        <div class="lightbox__prev" @click.stop.prevent="prev"><v-icon name="chevron-left"/></div>
        <div class="lightbox__next" @click.stop.prevent="next"><v-icon name="chevron-right"/></div>
    </div>
</template>

<script>
import './LightboxDirective'
import store from './LightboxStore'
import LightboxPic from './LightboxPic'

export default {
  name: 'lightbox',
  components: { LightboxPic },
  data () {
    return {
      state: store.state
    }
  },
  methods: {
    close () { store.close() },
    prev () { store.prev() },
    next () { store.next() }
  },
  computed: {
    image () {
        if (this.state.index !== false) {
            return this.state.images[this.state.group][this.state.index]
        }
        return false
    }
  }
}
</script>

<style src="./lightbox.scss" lang="scss"></style>
