<template>
  <div id="app" class="container">
    <header>
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <div class="container-fluid">
          <a class="navbar-brand" href="#">Trang Chủ</a>
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarSupportedContent"
            aria-controls="navbarSupportedContent"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
              <li class="nav-item">
                <a class="nav-link active" aria-current="page" href="#"
                  >Trang Chủ</a
                >
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">Về Chúng Tôi</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">Dịch Vụ</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">Liên Hệ</a>
              </li>
            </ul>
          </div>
        </div>
      </nav>
    </header>

    <main>
      <div class="jumbotron">
        <h1 class="display-4">Chào mừng bạn đến với trang chủ!</h1>
        <p class="lead">
          Đây là một trang web đơn giản được xây dựng bằng Vue.js và Bootstrap.
        </p>
        <hr class="my-4" />
        <p>Hãy khám phá và tận hưởng!</p>
      </div>
    </main>

    <footer class="text-center mt-5">
      <p>&copy; 2024 Trang Chủ. Đã được tạo bởi Vue.js và Bootstrap.</p>
    </footer>
  </div>
</template>

<script setup lang="ts">
// import { onMounted } from "vue";
// import { Modal } from "bootstrap";

// onMounted(() => {
//   const openModal = () => {
//     const modalElement = document.getElementById("exampleModal");
//     if (modalElement) {
//       const modal = new Modal(modalElement);
//       modal.show();
//     }
//   };
//   openModal();
// });
</script>
