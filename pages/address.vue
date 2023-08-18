<template>
    <MainLayout>
        <div
            id="AddressPage"
            class="mt-4 max-w-[500px] mx-auto px-2"
        >
            <div class="mx-auto bg-white rounded-lg p-3">
                <div class="text-xl text-bold mb-2">Address Details</div>

                <form @submit.prevent="submit()">
                    <TextInput
                        class="w-full"
                        placeholder="Contact Name"
                        v-model:inputmode="contactName"
                        inputType="text"
                        :error="error && error.type == 'contactName' ? error.message : ''"
                    />
                    <TextInput
                        class="w-full mt-2"
                        placeholder="Address"
                        v-model:inputmode="address"
                        inputType="text"
                        :error="error && error.type == 'address' ? error.message : ''"
                    />
                    <TextInput
                        class="w-full mt-2"
                        placeholder="Zip Code"
                        v-model:inputmode="zipCode"
                        inputType="text"
                        :error="error && error.type == 'zipCode' ? error.message : ''"
                    />
                    <TextInput
                        class="w-full mt-2"
                        placeholder="City"
                        v-model:inputmode="city"
                        inputType="text"
                        :error="error && error.type == 'city' ? error.message : ''"
                    />
                    <TextInput
                        class="w-full mt-2"
                        placeholder="Country"
                        v-model:inputmode="country"
                        inputType="text"
                        :error="error && error.type == 'country' ? error.message : ''"
                    />

                    <button>

                    </button>
                </form>
            </div>
        </div>
    </MainLayout>
</template>

<script setup>

import MainLayout from "~/layouts/MainLayout.vue";
</script>

