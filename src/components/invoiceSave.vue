<template>
    <hr class="bg-gradient-to-r h-1 border-none from-gray-700 mt-5" />
    <div class="actionbar text-right my-5">
        <button @click="addNewInvoice" class="purple-button">Kaydet</button>
    </div>
</template>
<script setup>
import { inject } from "vue";
const addNewInvoice = inject("addNewInvoice");
</script>
