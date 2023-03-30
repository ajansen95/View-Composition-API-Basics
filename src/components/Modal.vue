<template>
    <teleport to=".modals-container">
        <div class="modal">
            <h1><slot name="title"/></h1>
            <slot/>
            <button>Hide Modal</button>
        </div>
    </teleport>
</template>

<script setup>

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
