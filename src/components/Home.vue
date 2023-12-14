<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <h1>Home.vue</h1>
        <hr />
        <p>Components</p>
      </div>
      <div class="col-4 border p-1">
        <h2>Form control</h2>
        <div class="form-floating mb-3">
          <input type="email" class="form-control" id="floatingInput" placeholder="name@example.com">
          <label for="floatingInput">Email address</label>
        </div>
        <div class="form-floating">
          <input type="password" class="form-control" id="floatingPassword" placeholder="Password">
          <label for="floatingPassword">Password</label>
        </div>
        <button type="button" class="btn btn-primary mt-2">Submit</button>
      </div>
      <div class="col-4 border p-1">
        <h2>Modals</h2>
        <!-- Button trigger modal -->
        <button type="button" class="btn btn-primary" id="modalBtn" data-bs-toggle="modal" data-bs-target="#exampleModal">
          Launch modal
        </button>

        <!-- Modal -->
        <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
          <div class="modal-dialog">
            <div class="modal-content">
              <div class="modal-header">
                <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
              </div>
              <div class="modal-body">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit. Veniam maxime blanditiis impedit accusamus.
                Obcaecati, eaque. Ducimus, dolorem? Corporis quos, ad incidunt architecto, dicta porro itaque quis
                provident odio laudantium tempore!
              </div>
              <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                <button type="button" class="btn btn-primary" @click="saveModal">Save changes</button>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-4 border p-1">
        <h2>Toast here!</h2>
        <button type="button" class="btn btn-primary" id="liveToastBtn">
          Show live toast
        </button>

        <div class="toast-container position-fixed bottom-0 end-0 p-3">
          <div id="liveToast" class="toast" role="alert" aria-live="assertive" aria-atomic="true">
            <div class="toast-header">
              <img src="..." class="rounded me-2" alt="..." />
              <strong class="me-auto">Bootstrap</strong>
              <small>11 mins ago</small>
              <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close"></button>
            </div>
            <div class="toast-body">Hello, world! This is a toast message.</div>
          </div>
        </div>
      </div>
    <div class="col-4 border p-1">
      <a class="btn btn-outline-primary m-1" data-bs-toggle="offcanvas" href="#offcanvasExample" role="button" aria-controls="offcanvasExample">
  Link with href
</a>
<button class="btn btn-outline-success m-1" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasExample" aria-controls="offcanvasExample">
  Button with data-bs-target
</button>
<button class="btn btn-outline-dark m-1" type="button" id="offCanvasJS"  @click="openOffCanvas" aria-controls="offcanvasExample">
  Link via JS
</button>

<div class="offcanvas offcanvas-start" tabindex="-1" id="offcanvasExample" aria-labelledby="offcanvasExampleLabel">
  <div class="offcanvas-header">
    <h5 class="offcanvas-title" id="offcanvasExampleLabel">Offcanvas</h5>
    <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
  </div>
  <div class="offcanvas-body">
    <div>
      Some text as placeholder. In real life you can have the elements you have chosen. Like, text, images, lists, etc.
    </div>
    <div class="dropdown mt-3">
      <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown">
        Dropdown button
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item" href="#">Action</a></li>
        <li><a class="dropdown-item" href="#">Another action</a></li>
        <li><a class="dropdown-item" href="#">Something else here</a></li>
      </ul>
    </div>
  </div>
</div>
    </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted } from "vue";

onMounted(() => {
  initializeToast();
});

function initializeToast() {
  const toastTrigger = document.getElementById('liveToastBtn')
  const toastLiveExample = document.getElementById('liveToast')

  if (toastTrigger) {
    toastTrigger.addEventListener('click', () => {
      const toastBootstrap = bootstrap.Toast.getOrCreateInstance(toastLiveExample)
      toastBootstrap.show()
    })
  }
}

function saveModal() {
  var saveBtn = document.querySelector('.modal-footer button:nth-child(2)');
  saveBtn.classList.remove('btn-primary')
  saveBtn.classList.add('btn-success')
  saveBtn.innerHTML = 'Saved!'
  setTimeout(function () {
    const mymodal = document.getElementById('exampleModal')
    const modalInstance = bootstrap.Modal.getInstance(mymodal)
    modalInstance.hide()
  }, 2000)
  //revert button
  setTimeout(function () {
    saveBtn.classList.remove('btn-success')
    saveBtn.classList.add('btn-primary')
    saveBtn.innerHTML = 'Save changes'
  }, 3000)


}

function openOffCanvas() {
  const myOffcanvas = document.getElementById('offcanvasExample')
  const bsOffcanvas = new bootstrap.Offcanvas(myOffcanvas)
  bsOffcanvas.show()
}

</script>

<style scoped></style>
