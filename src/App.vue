<template>
  <h1>{{ title }}</h1>
  <p>Welcome..</p>
  <teleport v-if="showModal" to=".modals">
    <modal-item theme="" @close="toggleModal">
      <!-- named slots -->
      <template #links>
        <a href="#">sign up now </a>
        <a href="#">more info</a>
      </template>
      <!-- this is know as a slot -->
      <h1>Epiq Giveaway!</h1>
      <p>Grab you t-shirts for half price!!</p>
    </modal-item>
  </teleport>
  <button @click="toggleModal">Show Modal</button>

  <teleport v-if="showModalTwo" to=".modals">
    <modal-item theme="sale" @close="toggleModalTwo">
      <h3>Click now for some crazy stuff!!!</h3>
      <p>Promo codes</p>
    </modal-item>
  </teleport>
  <button @click="toggleModalTwo">Show Modal 2</button>
</template>

<script>
import ModalItem from "./components/ModalItem.vue";

export default {
  name: "App",
  components: {
    ModalItem,
  },
  data() {
    return {
      title: "My First Vue App!",
      header: "Sign up for our newsletter",
      text: "You wont regret it!",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      // reverse the current value of showModal
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
.actions {
  text-align: center;
  margin: 30px 0 10px 0;
}
.actions a {
  color: #333;
  padding: 8px;
  border: 1px solid #eee;
  border-radius: 5px;
  text-decoration: none;
  margin: 10px;
}
</style>
