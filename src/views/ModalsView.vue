<template>
  <div class="modals">
      <h1>Modals</h1>
      <button @click="showModal = true">Show Modal</button>
      <Modal
          v-if="showModal"
          title="My Modal title (via prop)"
      >
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Assumenda autem ex laboriosam sequi voluptates. A
              ab inventore nobis. A alias aliquam dolor dolore ea eaque nihil omnis quis reiciendis tempore.</p>
      </Modal>
  </div>
</template>

<script setup>
/*
    imports
 */

    import {ref} from "vue";
    import Modal from "@/components/Modal.vue";

/*
    modals
 */

    const showModal = ref(false)

</script>

<!--
<script>
import Modal from "@/components/Modal.vue";
export default {
    components: {
        Modal
    }
}
</script>
-->