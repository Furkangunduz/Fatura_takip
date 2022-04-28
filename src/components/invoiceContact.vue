<template>
    <div>
        <h3 class="text-gray-400 text-xl">Fatura Bilgileri</h3>
        <hr class="bg-gradient-to-r h-[1px] border-none from-gray-700 mb-2" />
        <div>
            <label for="client_name" class="flex flex-col text-gray-400 mb-2">
                <small class="mb-1">Müşteri Adı</small>
                <input
                    v-model="user.fullName"
                    autocomplete="off"
                    id="client_name"
                    class="input"
                    type="text"
                />
            </label>
            <label for="client_email" class="flex flex-col text-gray-400 mb-2">
                <small class="mb-1">E-posta</small>
                <input
                    v-model="user.email"
                    autocomplete="off"
                    id="client_email"
                    class="input"
                    type="email"
                />
            </label>

            <div class="grid grid-cols-3 gap-5">
                <label for="city" class="flex flex-col text-gray-400 mb-2">
                    <small class="mb-1">Şehir</small>
                    <input
                        v-model="user.city"
                        autocomplete="off"
                        id="city"
                        class="input"
                        type="text"
                    />
                </label>
                <label for="zip_code" class="flex flex-col text-gray-400 mb-2">
                    <small class="mb-1">Posta Kodu</small>
                    <input
                        v-model="user.zipCode"
                        autocomplete="off"
                        id="zip_code"
                        class="input"
                        type="text"
                    />
                </label>
                <label for="country" class="flex flex-col text-gray-400 mb-2">
                    <small class="mb-1">Ülke</small>
                    <input
                        v-model="user.country"
                        autocomplete="off"
                        id="country"
                        class="input"
                        type="text"
                    />
                </label>
            </div>
        </div>
    </div>
</template>
<script setup>
import { inject } from "@vue/runtime-core";
const user = inject("user");
</script>
