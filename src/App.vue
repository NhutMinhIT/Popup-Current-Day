<!-- App.vue -->
<template>
  <div>
    <button type="button" class="btn" @click="showModal">Open Modal!</button>
    <Popup v-show="isModalVisible" @close="closeModal">
      <template v-slot:header>This is a new modal header.</template>
      <template v-slot:body>This is a new modal body.</template>
      <template v-slot:footer>This is a new modal footer.</template>
    </Popup>
  </div>
</template>

<script>
import Popup from "@/components/Popup/PopupComponent.vue"; // Adjust the path accordingly

export default {
  components: { Popup },
  data() {
    return {
      isModalVisible: true,
    };
  },
  mounted() {
    // Check if modal has been shown today
    const modalShownToday = localStorage.getItem("modalShownDate");
    const currentDate = new Date().toDateString();

    if (modalShownToday !== currentDate) {
      this.isModalVisible = true;
      localStorage.setItem("modalShownDate", currentDate);
    } else {
      this.isModalVisible = false; // Set isModalVisible to false if modal has been shown today
    }
  },
  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    },
  },
};
</script>

<style>
.btn {
  z-index: 0;
  position: absolute;
  left: 50%;
  top: 40%;
}
</style>
