<template>
    <div class="main">
        <app-side-bar />
        <section class="section">
            <invoice-contact />
            <invoice-items />
            <invoice-summary />
            <invoice-save />
        </section>
    </div>
</template>

<script setup>
import appSideBar from "./components/appSideBar.vue";
import invoiceContact from "./components/invoiceContact.vue";
import invoiceItems from "./components/invoiceItems.vue";
import invoiceSummary from "./components/invoiceSummary.vue";
import invoiceSave from "./components/invoiceSave.vue";

import { provide, reactive } from "@vue/runtime-core";


const state = reactive({
    user: {
        fullName: null,
        email: null,
        city: null,
        zipCode: null,
        country: null,
    },
    itemList: [],
    invoiceList: [],
});
const addNewInvoice = () => {
    state.invoiceList.push({
        id: "" + new Date().getTime(),
        user: JSON.parse(JSON.stringify(state.user)),
        itemList: JSON.parse(JSON.stringify(state.itemList)),
    });

    Object.keys(state.user).forEach((field) => {
        state.user[field] = null;
    });

    state.itemList.length = 0;
};

const showInvoice = (id) => {
    const invoice = state.invoiceList.find((item) => item.id == id);
    Object.keys(state.user).forEach((field) => {
        state.user[field] =
            invoice.user[field] == null ? "" : invoice.user[field];
    });
    console.log(invoice.itemList);
    invoice.itemList.forEach((item) => {
        state.itemList.push(item);
    });
    state.itemList.length = invoice.itemList.length;
};

provide("user", state.user);
provide("itemList", state.itemList);
provide("invoiceList", state.invoiceList);
provide("addNewInvoice", addNewInvoice);
provide("showInvoice", showInvoice);
</script>
