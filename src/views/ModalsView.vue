<template>
  <div class="modals">
      <h1>Modals</h1>
      <button @click="showModal = true">Show Modal</button>
      <teleport to=".modals-container">
          <div class="modal" v-if="showModal">
              <h1>This is a modal</h1>
              <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Assumenda autem ex laboriosam sequi voluptates. A
                  ab inventore nobis. A alias aliquam dolor dolore ea eaque nihil omnis quis reiciendis tempore.</p>
              <button @click="showModal = false">Hide Modal</button>
          </div>
      </teleport>
  </div>
</template>

<script setup>
/*
    imports
 */

    import {ref} from "vue";

/*
    modals
 */

    const showModal = ref(false)

</script>

<style scoped>
.modal{
    background: beige;
    padding: 10px;
    color: #282828;
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    z-index: 1000;
}
</style>