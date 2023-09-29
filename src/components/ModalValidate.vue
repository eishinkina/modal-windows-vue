<template>
  <Modal title="modal with form + Validate" @close="$emit('close')">
    <div slot="body">
      <form @submit.prevent="onSubmit">
        <!-- name  -->
        <div class="form-item" :class="{ errorInput: $v.name.$error }">
          <label>Name:</label>
          <p class="errorText" v-if="!$v.name.required">filed is required</p>
          <p class="errorText" v-if="!$v.name.minLength">
            Name must have at least {{ $v.name.$params.minLength.min }}!
          </p>
          <input
            v-model="name"
            @change="$v.name.$touch()"
            :class="{ error: $v.name.$error }"
          />
        </div>
        <!-- email  -->
        <div class="form-item" :class="{ errorInput: $v.email.$error }">
          <label>email:</label>
          <p class="errorText" v-if="!$v.email.required">filed is required</p>
          <p class="errorText" v-if="!$v.email.email">email is not correct!</p>
          <input
            v-model="email"
            @change="$v.email.$touch()"
            :class="{ error: $v.email.$error }"
          />
        </div>
        <!-- button  -->
        <button class="btn btnPrimary">submit</button>
      </form>
    </div>
  </Modal>
</template>

<script>
import Modal from "./Modal.vue";
import { required, minLength, email } from "vuelidate/lib/validators";

export default {
  components: {
    Modal,
  },
  data() {
    return {
      name: "",
      email: "",
    };
  },
  validations: {
    name: {
      required,
      minLength: minLength(4),
    },
    email: {
      required,
      email,
    },
  },
  methods: {
    onSubmit() {
      this.$v.$touch();
      if (this.$v.$invalid) {
        const user = {
          name: this.name,
          email: this.email,
        };
        console.log(user);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.form-item .errorText {
  display: none;
  margin-bottom: 8px;
  font-size: 13px;
  color: red;
}

.form-item {
  &.errorInput .errorText {
    display: block;
  }
}

.input.error {
  border-color: red;
}
</style>
