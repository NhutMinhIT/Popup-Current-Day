<template>
  <div
    class="modal fade"
    id="exampleModal"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
          <button
            type="button"
            class="btn-close"
            @click="closeModal"
            data-bs-dismiss="modal"
            aria-label="Close"
          >
            X
          </button>
        </div>
        <div class="modal-body">
          <h2 class="modal-title" id="exampleModalLabel">Modal title</h2>
          <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
          <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted } from "vue";
import { Modal } from "bootstrap";

const closeModal = () => {
  Modal.getInstance("#exampleModal").hide();
  localStorage.setItem("lastClosedTime", new Date().getTime().toString());
};

onMounted(() => {
  const lastClosedTime = localStorage.getItem("lastClosedTime");
  console.log("lastClosedTime " + lastClosedTime);

  const currentTime = new Date().getTime();
  console.log("currentTime" + currentTime);

  const timeDifference = currentTime - parseInt(lastClosedTime || "0");
  console.log("timeDifference" + timeDifference);

  // Nếu chưa từng đóng hoặc đã đóng hơn 24 giờ
  if (!lastClosedTime || timeDifference >= 24 * 60 * 60 * 1000) {
    Modal.getOrCreateInstance("#exampleModal").show();
  }
});
</script>

<style>
.modal {
  background: #ffffff;
  box-shadow: 2px 2px 20px 1px rgba(0, 0, 0, 0.2);
  overflow-x: auto;
  width: 300px;
  height: 300px;
  display: flex;
  flex-direction: column;
  z-index: 5000;
}

.modal-header,
.modal-footer {
  padding: 15px;
  display: flex;
}

.modal-header {
  position: relative;
  border-bottom: 1px solid #eeeeee;
  color: #4aae9b;
  background: white;
  justify-content: space-between;
}

.modal-footer {
  border-top: 1px solid #eeeeee;
  flex-direction: column;
  justify-content: flex-end;
  color: #4aae9b;
}

.modal-body {
  position: relative;
  padding: 20px 10px;
  color: #4aae9b;
  background: white;
}

.btn-close {
  position: relative;
  top: 0;
  right: 0;
  color: #4aae9b;
  border: none;
  font-size: 20px;
  padding: 10px;
  cursor: pointer;
  font-weight: bold;
  background: white;
}

.btn-green {
  color: white;
  background: #4aae9b;
  border: 1px solid #4aae9b;
  border-radius: 2px;
}

.modal-fade-enter,
.modal-fade-leave-to {
  opacity: 0;
}

.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.5s ease;
}
</style>
