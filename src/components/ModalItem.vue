<template>
  <!-- .self makes it so you when you click on the actual modal it wont close, you gotta click outside of it -->
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot></slot>
      <div class="actions">
        <!-- named slots -->
        <slot name="links"></slot>
      </div>
      <!-- <h1>{{ header }}</h1>
      <p>{{ text }}</p> -->
    </div>
  </div>
</template>

<script>
export default {
  props: {
    header: {
      type: String,
      required: true,
    },
    text: {
      type: String,
      required: true,
    },
    theme: {
      type: String,
      default: "default",
    },
  },
  emits: ["close"],
  methods: {
    closeModal() {
      // custom emit event]
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background-color: white;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal h1 {
  color: dodgerblue;
  border: none;
  padding: 0;
}
.modal p {
  font-style: normal;
}

.modal.sale {
  background-color: crimson;
  color: white;
}
.modal.sale h1 {
  color: white;
}
.modal.sale .actions {
  color: white;
}
.modal.sale .actions a {
  color: white;
}

.modal.crazy {
  background-color: green;
  color: white;
}
</style>
