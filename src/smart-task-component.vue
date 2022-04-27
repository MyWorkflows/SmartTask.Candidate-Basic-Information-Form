<script lang="ts">
import { defineComponent } from "vue";


export default defineComponent({
  name: "SmartTaskComponent", // vue component name
  props: ['componentState', 'componentStatus'],
  data() {
    return { model: {} };
  },
  computed: {},
  methods: {
    async submitForm() {
      this.$emit("execute-smart-task", this.model);
    },
  },
  created() {
    if (this.componentState) {
      this.model = this.componentState;
    }
  },
  setup() {},
});
</script>

<template>
  <form>
    <div class="row">
      <div class="col">
        <div class="mb-3">
          <label class="form-label">First name</label
          ><input
            v-model="model.firstName"
            type="text"
            class="form-control"
          />
        </div>
      </div>
      <div class="col">
        <div class="mb-3">
          <label class="form-label">Last name</label
          ><input
            v-model="model.lastName"
            type="text"
            class="form-control"
          />
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <div class="mb-3">
          <label class="form-label">Email address</label
          ><input
            type="email"
            class="form-control"
            id="exampleInputEmail1"
            aria-describedby="emailHelp"
            v-model="model.emailAddress"
          />
          <div id="emailHelp" class="form-text">
            We'll never share your email with anyone else.
          </div>
        </div>
      </div>
      <div class="col">
        <div class="mb-3">
          <label class="form-label">Phone number</label
          ><input
            type="phone"
            v-model="model.phoneNumber"
            class="form-control"
          />
        </div>
      </div>
    </div>
    <div class="mb-3">
      <label class="form-label">Address line 1</label
      ><input
        type="text"
        v-model="model.addressLine1"
        class="form-control"
      />
    </div>
    <div class="mb-3">
      <label class="form-label">Address line 2</label
      ><input
        type="text"
        v-model="model.addressLine2"
        class="form-control"
      />
    </div>
    <div class="row">
      <div class="col">
        <div class="mb-3">
          <label class="form-label">City</label
          ><input
            type="text"
            v-model="model.city"
            class="form-control"
          />
        </div>
      </div>
      <div class="col">
        <div class="mb-3">
          <label class="form-label">Postal/Zip code</label
          ><input
            type="number"
            v-model="model.postalCode"
            class="form-control"
          />
        </div>
      </div>
    </div>
    <div class="mb-3">
      <label class="form-label">Country/Region</label
      ><input
        type="text"
        v-model="model.country"
        class="form-control"
      />
    </div>
    <div class="my-5">
      <button
        type="button"
        @click="submitForm"
        class="float-end btn btn-success"
      >
        Save and complete
      </button>
    </div>
  </form>
</template>


