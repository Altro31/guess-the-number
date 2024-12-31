<script setup lang="ts">

const count = ref(0);

socket.on("increment", () => {
    console.log("Incrementing count");
    count.value++
})

function handleIncrement() {
    socket.emit("increment");
}

</script>

<template>
    <button @click="handleIncrement()" class="text-white border-white rounded-md p-2 px-3">Count {{ count }}</button>
</template>
