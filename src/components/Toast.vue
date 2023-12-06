<!-- Toast.vue -->
<template>
    <div>
      <div
        v-if="show"
        class="toast"
        role="alert"
        aria-live="assertive"
        aria-atomic="true"
      >
        <div class="toast-header">
          <strong class="me-auto">{{ title }}</strong>
          <button
            type="button"
            class="btn-close"
            @click="closeToast"
            aria-label="Cerrar"
          ></button>
        </div>
        <div class="toast-body">{{ message }}</div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      show: {
        type: Boolean,
        default: false,
      },
      title: {
        type: String,
        default: "Aviso",
      },
      message: {
        type: String,
        required: true,
      },
    },
    methods: {
      closeToast() {
        this.$emit("close");
      },
    },
  };
  </script>
  
  <style scoped>
  /* Puedes personalizar los estilos del Toast aquí */
  </style>
  