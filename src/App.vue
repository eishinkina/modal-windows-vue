<template>
  <div class="wrapper">
    <!-- header  -->
    <div class="wrapper-content">
      <section>
        <div class="container">
          <button class="btn btnPrimary" @click="modalFirst = !modalFirst">Show first modal</button>
          <!-- first modal  -->
          <Modal title="first modal" v-show="modalFirst" @close="modalFirst = !modalFirst">
            <div slot="body">
              <p>text text text text</p>
              <button class="btn btnPrimary" @click="modalFirst = !modalFirst">Well done!</button>
            </div>
          </Modal>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import Modal from './components/Modal.vue';
export default {
  components: {
    Modal,
  },
  data() {
    return {
      modalFirst: false
    }
  }
}
</script>

<style lang="scss" scoped></style>
