<template>
  <div class="card my-3" style="width: auto">
    <VeeForm
      @submit="onSubmit"
      :validation-schema="heroYupValidation"
      class="card-header"
      style="min-width: 460px"
    >
      <div class="d-flex flex-column">
        <section class="form-group">
          <label for="firstName" class="mr-4">First Name</label>
          <ErrorMessage name="firstName" class="text-danger" />
          <Field
            id="firstName"
            v-model="obj.firstName"
            placeholder="📛"
            autocomplete="off"
            name="firstName"
            as="input"
            type="text"
            class="form-control"
          />
        </section>

        <section class="form-group">
          <label for="lastName" class="mr-4">Last Name</label>
          <ErrorMessage name="lastName" class="text-danger" />
          <Field
            id="lastName"
            v-model="obj.lastName"
            placeholder="📛"
            autocomplete="off"
            name="lastName"
            as="input"
            type="text"
            class="form-control"
          />
        </section>
        <section class="form-group">
          <label for="house" class="mr-4">House</label>
          <ErrorMessage name="house" class="text-danger" />
          <Field
            id="house"
            v-model="obj.house"
            placeholder="🏠"
            autocomplete="off"
            name="house"
            as="input"
            type="text"
            class="form-control"
          />
        </section>
        <section class="form-group">
          <label for="knownAs" class="mr-4">Known as</label>
          <ErrorMessage name="knownAs" class="text-danger" />
          <Field
            id="knownAs"
            v-model="obj.knownAs"
            placeholder="👀"
            autocomplete="off"
            name="knownAs"
            as="input"
            type="text"
            class="form-control"
          />
        </section>
        <button type="submit" class="btn btn-success">
          {{ text }}
        </button>
      </div>
    </VeeForm>
  </div>
</template>

<script>
import { Field, Form as VeeForm, ErrorMessage } from "vee-validate";
import { heroYupValidation } from "./heroYupValidation";

export default {
  name: "Form",
  components: {
    VeeForm,
    Field,
    ErrorMessage,
  },
  data: () => ({
    heroYupValidation,
  }),
  props: {
    text: {
      type: String,
      default: () => String,
    },
    obj: {
      type: Object,
      default: () => {},
    },
  },
  methods: {
    onSubmit() {
      this.$emit("handleSubmit");
    },
  },
};
</script>

<style scoped></style>
