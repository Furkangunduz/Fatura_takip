<template>
    <aside class="bg-gray-700 w-[300px] h-screen">
        <h3 class="text-2xl font-bold mt-2 p-2">Fatura Listesi</h3>
        <side-bar-item
            v-for="(invoice, indx) in invoiceList"
            :key="indx"
            :item="invoice"
        />
    </aside>
</template>

<script setup>
import { inject } from "@vue/runtime-core";
import SideBarItem from "./SideItem.vue";

const invoiceList = inject("invoiceList");
</script>
