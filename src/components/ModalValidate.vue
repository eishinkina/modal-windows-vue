<template>
    <Modal title="modal with form + Validate" @close="$emit('close')">
        <div slot="body">
            <form @submit.prevent="">
                <label>Name:</label>
                <input type="text">
                <label>email</label>
                <input type="email">
                <button class="btn btnPrimary">submit</button>
            </form>
        </div>
    </Modal>
</template>

<script>
import Modal from './Modal.vue'
export default {
    components: {
        Modal,
    }

}
</script>

<style lang="scss" scoped></style>