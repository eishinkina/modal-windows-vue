<template>
  <div class="wrapper">
    <!-- header  -->
    <div class="wrapper-content">
      <section>
        <div class="container">
          <!-- first modal  -->
          <button class="btn btnPrimary" @click="modalFirst = !modalFirst">Show first modal</button>
          <Modal title="first modal" v-show="modalFirst" @close="modalFirst = false">
            <div slot="body">
              <p>text text text text</p>
              <button class="btn btnPrimary" @click="modalFirst = !modalFirst">Well done!</button>
            </div>
          </Modal>
          <!-- second modal  -->
          <button class="btn btnPrimary" @click="modalSecond.show = !modalSecond.show">Show modal with form</button>
          <Modal title="modal with show" v-show="modalSecond.show" @close="modalSecond.show = false">
            <div slot="body">
              <form @submit.prevent="submitSecondForm">
                <label>Name:</label>
                <input type="text" required v-model="modalSecond.name">
                <label>email</label>
                <input type="email" required v-model="modalSecond.email">
                <button class="btn btnPrimary">submit</button>
              </form>
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
      modalFirst: false,
      modalSecond: {
        show: false,
        name: '',
        email: '',
      }
    }
  },
  methods: {
    submitSecondForm() {
      console.log({
        name: this.modalSecond.name,
        email: this.modalSecond.email
      })
      this.modalSecond.name = ''
      this.modalSecond.email = ''
      this.modalSecond.show = false
    }
  }
}
</script>

<style lang="scss" scoped></style>
