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

                    <button
                      :disabled="isWorking"
                      type="submit"
                      class="mt-6 bg-gradient-to-r from-[#FE630C] to-[#FF3200] w-full text-white text-[21px] font-semibold p-1.5 rounded-full"
                    >
                      <div v-if="!isWorking">Update Address</div>
                      <Icon
                        v-else
                        name="eos-icons:loading"
                        size="25"
                        class="mr-2"
                      />
                    </button>
                </form>
            </div>
        </div>
    </MainLayout>
</template>

<script setup>

import MainLayout from "~/layouts/MainLayout.vue";
import { useUserStore } from "~/stores/user";
const userStore = useUserStore();

let contactName = ref(null);
let address = ref(null);
let zipCode = ref(null);
let city = ref(null);
let country = ref(null);
let currentAddress = ref(null);
let isUpdate = ref(null);
let isWorking = ref(null);
let error = ref(null);

watchEffect(() => {

});

const submit = async () => {
  isWorking.value = true;
  error.value = null

  if(!contactName.value) {
    error.value = {
      type: 'contactName',
      message: 'A contact name is required'
    }
  } else if (!address.value) {
    error.value = {
      type: 'address',
      message: 'An address is required'
    }
  } else if (!zipCode.value) {
    error.value = {
      type: 'zipCode',
      message: 'A zip code is required'
    }
  } else if (!city.value) {
    error.value = {
      type: 'city',
      message: 'A city is required'
    }
  } else if (!country.value) {
    error.value = {
      type: 'country',
      message: 'A country is required'
    }
  }

  if (error.value) {
    isWorking.value = false

  }

  // add here
}
</script>

