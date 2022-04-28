<template>
    <div>
        <div class="summary mt-5 flex justify-end items-end">
            <div class="text-right mr-2">
                <div class="text-gray-400">KDV Toplam :</div>
                <div class="text-gray-300">Genel Toplam :</div>
            </div>
            <div class="text-right">
                <div class="text-gray-400">{{ kdv }}</div>
                <div class="text-gray-300">{{ total }}</div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { watch, inject, ref } from "@vue/runtime-core";

const itemList = inject("itemList");
let total = ref(0);
let kdv = ref(0);
watch(itemList, () => {
    itemList.forEach((element) => {
        total.value = (element.price * element.qty).toFixed(2);
    });
    kdv.value = (total.value * 0.18).toFixed(2);
});
</script>
