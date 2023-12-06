<template>
  <div class="container">
    <div class="row">
      <div class="col-8">
        <h1>Home</h1>
        <hr />
        <p><i class="fa-solid fa-user"></i> Home page content goes here.</p>
      </div>
      <div class="col-4">
        <h2>Toast here!</h2>
        <hr />
        <button type="button" class="btn btn-primary" id="liveToastBtn">
          Show live toast
        </button>

        <div class="toast-container position-fixed bottom-0 end-0 p-3">
          <div
            id="liveToast"
            class="toast"
            role="alert"
            aria-live="assertive"
            aria-atomic="true"
          >
            <div class="toast-header">
              <img src="..." class="rounded me-2" alt="..." />
              <strong class="me-auto">Bootstrap</strong>
              <small>11 mins ago</small>
              <button
                type="button"
                class="btn-close"
                data-bs-dismiss="toast"
                aria-label="Close"
              ></button>
            </div>
            <div class="toast-body">Hello, world! This is a toast message.</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted } from "vue";

name: "Home",
  onMounted(() => {
        initializeToast();
  });
  methods: {
    initializeToast() {
        const toastTrigger = document.getElementById('liveToastBtn')
        const toastLiveExample = document.getElementById('liveToast')

        if (toastTrigger) {
            toastTrigger.addEventListener('click', () => {
            const toastBootstrap = bootstrap.Toast.getOrCreateInstance(toastLiveExample)
            toastBootstrap.show()
            })
        }
    }
  };
</script>

<style scoped></style>
```
