<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <h1>Bootstrap components in VueJS</h1>
        <p>Bienvenido a nuestra aplicación interactiva construida con Vue.js, donde exploraremos una selección de potentes componentes proporcionados por Bootstrap. Esta aplicación te permitirá experimentar con diversos elementos de interfaz de usuario que facilitan la creación de diseños modernos y receptivos. </p>
        <p>Puedes encontrar toda la documentación en <a href="https://getbootstrap.com/docs/5.3/getting-started/introduction/" target="_blank">su web oficial</a></p>
      </div>
      <div class="col-5 border p-1 m-2"> <!--Form control-->
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
      <div class="col-3 border p-1 m-2"> <!--Modals-->
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
      <div class="col-3 border p-1 m-2"> <!--Toast-->
        <h2>Toast</h2>
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
      <div class="col-4 border p-1 m-2"> <!--Offcanvas-->
        <h2>OffCanvas</h2>
        <a class="btn btn-outline-primary m-1" data-bs-toggle="offcanvas" href="#offcanvasExample" role="button"
          aria-controls="offcanvasExample">
          Link with href
        </a>
        <button class="btn btn-outline-success m-1" type="button" data-bs-toggle="offcanvas"
          data-bs-target="#offcanvasExample" aria-controls="offcanvasExample">
          Button with data-bs-target
        </button>
        <button class="btn btn-outline-dark m-1" type="button" id="offCanvasJS" @click="openOffCanvas"
          aria-controls="offcanvasExample">
          Link via JS
        </button>

        <div class="offcanvas offcanvas-start" tabindex="-1" id="offcanvasExample"
          aria-labelledby="offcanvasExampleLabel">
          <div class="offcanvas-header">
            <h5 class="offcanvas-title" id="offcanvasExampleLabel">Offcanvas</h5>
            <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
          </div>
          <div class="offcanvas-body">
            <div>
              Some text as placeholder. In real life you can have the elements you have chosen. Like, text, images, lists,
              etc.
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
      <div class="col-3 border p-1 m-2"> <!--Badge-->
        <h2>Badge</h2>
        <button type="button" class="btn btn-primary position-relative m-2">
          Inbox
          <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger">
            {{ msg }}
            <span class="visually-hidden">unread messages</span>
          </span>
        </button>
        <div><button type="button" @click="msg++" class="btn btn-outline-success m-2">Send message</button></div>
      </div>
      <div class="col-4 border p-1 m-2"> <!--Popover-->
        <h2>Popover</h2>
        <button type="button" class="btn btn-lg btn-success" data-bs-toggle="popover" data-bs-title="Popover title"
          data-bs-content="And here's some amazing content. It's very engaging. Right?">Click to toggle popover</button>
      </div>
      <div class="col-6 border p-1 m-2"> <!--Progress & spinners-->
        <h2>Progress & spinners</h2>
        <button class="btn btn-primary m-2" id="loadButton" type="button" @click="load" :disabled="loading">
          <span id="spinner" v-if="loading"
            class="spinner-border spinner-border-sm" aria-hidden="true"></span>
          <span role="status">Load</span>
        </button>
        <div class="progress" id="progressbar" role="progressbar" aria-label="Animated striped example"
          aria-valuenow="{{ progress }}" aria-valuemin="0" aria-valuemax="100">
          <div class="progress-bar progress-bar-striped progress-bar-animated" :style="{ width: progress + '%' }"></div>
        </div>

      </div>
      <div class="col-5 border p-1 m-2"> <!--Tooltips-->
        <h2>Tooltip</h2>
        <div class="row justify-content-evenly">
          <button type="button" class="btn btn-outline-success col-2" data-bs-toggle="tooltip" data-bs-placement="top"
            data-bs-title="Tooltip on top">
            Tooltip on top
          </button>
          <button type="button" class="btn btn-outline-primary col-2" data-bs-toggle="tooltip" data-bs-placement="right"
            data-bs-title="Tooltip on right">
            Tooltip on right
          </button>
          <button type="button" class="btn btn-outline-danger col-2 " data-bs-toggle="tooltip" data-bs-placement="bottom"
            data-bs-title="Tooltip on bottom">
            Tooltip on bottom
          </button>
          <button type="button" class="btn btn-outline-dark col-2 " data-bs-toggle="tooltip" data-bs-placement="left"
            data-bs-title="Tooltip on left">
            Tooltip on left
          </button>
        </div>

      </div>
      <div class="col-12 border p-1 m-2"> <!--Scrollspy-->
        <h2>Scrollspy</h2>
        <div class="row">
          <div class="col-4">
            <div id="list-example" class="list-group">
              <a class="list-group-item list-group-item-action" href="#list-item-1">Item 1</a>
              <a class="list-group-item list-group-item-action" href="#list-item-2">Item 2</a>
              <a class="list-group-item list-group-item-action" href="#list-item-3">Item 3</a>
              <a class="list-group-item list-group-item-action" href="#list-item-4">Item 4</a>
            </div>
          </div>
          <div class="col-8">
            <div data-bs-spy="scroll" data-bs-target="#list-example" data-bs-smooth-scroll="true"
              class="scrollspy-example" tabindex="0">
              <h4 id="list-item-1">Item 1</h4>
              <p>Bootstrap es un popular framework de diseño web que facilita la creación de interfaces modernas y
                receptivas. Una de las características destacadas de Bootstrap es ScrollSpy, un componente que permite
                resaltar automáticamente los elementos de la barra de navegación según la posición del usuario en la
                página.</p>
              <h4 id="list-item-2">Item 2</h4>
              <p>ScrollSpy funciona monitorizando la posición de desplazamiento vertical del usuario en la página. Cuando
                el usuario se desplaza hacia abajo o hacia arriba, ScrollSpy detecta qué sección de la página está visible
                en la ventana del navegador. Esta información se utiliza para resaltar automáticamente el enlace
                correspondiente en la barra de navegación.</p>
              <p>Implementar ScrollSpy en tu proyecto Bootstrap puede mejorar significativamente la navegación,
                especialmente en páginas largas con múltiples secciones. </p>
              <h4 id="list-item-3">Item 3</h4>
              <p>Para implementar ScrollSpy en un proyecto Bootstrap, primero debes incluir la biblioteca JavaScript de
                Bootstrap en tu HTML. Luego, debes agregar la clase scrollspy a la etiqueta del elemento contenedor que
                engloba las secciones de tu página que deseas seguir. Además, debes asignar las etiquetas de enlace en tu
                barra de navegación con el atributo data-target que apunte a los identificadores de las secciones que
                deseas vincular.</p>
              <h4 id="list-item-4">Item 4</h4>
              <p>Bootstrap también ofrece opciones para personalizar el comportamiento de ScrollSpy. Puedes ajustar la
                velocidad de transición, el límite de desplazamiento y más. Además, puedes aprovechar los eventos
                JavaScript proporcionados por Bootstrap, como activate.bs.scrollspy, para realizar acciones personalizadas
                cuando se activa una sección específica. Esto permite una experiencia de usuario más rica y adaptada a las
                necesidades de tu proyecto.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";

const msg = ref(0);
const progress = ref(0);
const loading = ref(false);

onMounted(() => {
  initializeToast();
  initializePopover();
  initializeTooltip();
});

function load() {
  loading.value = true;
  progress.value = 0;
  const interval = setInterval(() => {
    progress.value += 20;
    document.getElementById('progressbar').setAttribute('aria-valuenow', progress.value);
    if (progress.value >= 100) {
      clearInterval(interval);
      document.querySelector('#progressbar > div').classList.remove('progress-bar-animated');
      document.querySelector('#progressbar > div').classList.remove('progress-bar-striped');
      document.querySelector('#progressbar > div').classList.add('bg-success');
      loading.value = false;
    }
  }, 1000);

}

function initializeTooltip() {
  var tooltipTriggerList = [].slice.call(document.querySelectorAll('[data-bs-toggle="tooltip"]'))
  var tooltipList = tooltipTriggerList.map(function (tooltipTriggerEl) {
    return new bootstrap.Tooltip(tooltipTriggerEl)
  })
}

function initializePopover() {
  var popoverTriggerList = [].slice.call(document.querySelectorAll('[data-bs-toggle="popover"]'))
  var popoverList = popoverTriggerList.map(function (popoverTriggerEl) {
    return new bootstrap.Popover(popoverTriggerEl)
  })
}

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

<style scoped>.scrollspy-example {
  height: 160px;
  margin-top: .5rem;
  overflow: auto;
}</style>
