<template>
  <div class="wrapper">
    <!-- header  -->
    <div class="wrapper-content">
      <section>
        <div class="container">
          <Modal title="first modal"></Modal>
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
      
    }
  }
}
</script>

<style lang="scss" scoped>
.wrapper {
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
  min-height: 100vh;

  .wrapper-content {
    padding: 20px;

    section {
      /* margin: 20px 0; */
      /* background-color: #ffffff; */
      /* border-radius: 10px; */

      .container {
        max-width: 1200px;
        margin: 0 auto;
        padding: 20px;

        h1 {
          color: #333333;
          font-size: 24px;
          /* text-align: center; */
          margin-top: 20px;
        }
      }
    }
  }
}
</style>
