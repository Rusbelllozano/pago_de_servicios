<template>
  <div class="w-full h-screen absolute top-0 bg-gray-500/50">
    <div class="mx-auto max-w-2xl bg-white pt-10">
      <section
        aria-labelledby="payment-and-shipping-heading"
        class="py-16 lg:max-w-lg lg:w-full lg:mx-auto lg:pt-0 lg:pb-24 lg:row-start-1 lg:col-start-1"
      >
        <span
          class="cursor-pointer font-bold text-lg"
          @click="props.closeModal"
        >
          X
        </span>
        <h2 id="payment-and-shipping-heading" class="sr-only">
          Detalles de pago
        </h2>

        <form  @submit.prevent="payNow">
          <div class="max-w-2xl mx-auto px-4 lg:max-w-none lg:px-0">
            <div>
              <h3
                id="contact-info-heading"
                class="text-lg font-medium text-gray-900"
              >
                Información de contacto
              </h3>

              <div class="mt-6">
                <label
                  for="email-address"
                  class="block text-sm font-medium text-gray-700"
                  >Correo Electronico</label
                >
                <div class="mt-1">
                  <input
                    type="email"
                    id="email-address"
                    name="email-address"
                    autocomplete="email"
                    class="block w-full border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                  />
                </div>
              </div>
            </div>

            <div class="mt-10">
              <h3 class="text-lg font-medium text-gray-900">
                Detalles de pago
              </h3>

              <div class="mt-6 grid grid-cols-3 sm:grid-cols-4 gap-y-6 gap-x-4">
                <div class="col-span-3 sm:col-span-4">
                  <label
                    for="card-number"
                    class="block text-sm font-medium text-gray-700"
                    >Numero de tarjeta</label
                  >
                  <div class="mt-1">
                    <input
                      type="text"
                      id="card-number"
                      name="card-number"
                      autocomplete="cc-number"
                      class="block w-full border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                    />
                  </div>
                </div>

                <div class="col-span-2 sm:col-span-3">
                  <label
                    for="expiration-date"
                    class="block text-sm font-medium text-gray-700"
                    >Fecha de expiración (MM/YY)</label
                  >
                  <div class="mt-1">
                    <input
                      type="text"
                      name="expiration-date"
                      id="expiration-date"
                      autocomplete="cc-exp"
                      class="block w-full border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                    />
                  </div>
                </div>

                <div>
                  <label
                    for="cvc"
                    class="block text-sm font-medium text-gray-700"
                    >CVC</label
                  >
                  <div class="mt-1">
                    <input
                      type="text"
                      name="cvc"
                      id="cvc"
                      autocomplete="csc"
                      class="block w-full border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                    />
                  </div>
                </div>
              </div>
            </div>

            <div class="mt-10">
              <h3 class="text-lg font-medium text-gray-900">
                Información de factura
              </h3>
              <h4 class="pt-5">Nombre factura - Codigo Convenio</h4>
              <div class="pt-2 flex items-center gap-3">
                <span
                  :class="[
                    props.currentInvoice.iconBackground,
                    props.currentInvoice.iconForeground,
                    'rounded-lg inline-flex p-3 ring-4 ring-white',
                  ]"
                >
                  <component
                    :is="props.currentInvoice.icon"
                    class="h-6 w-6"
                    aria-hidden="true"
                  />
                </span>
                <p class="text-md font-light">
                  {{ props.currentInvoice.name }}
                </p>
              </div>
              <h4 class="pt-5">Valor Factura</h4>
              <p class="text-md font-light">
                ${{ props.currentInvoice.price }}
              </p>
              <div class="mt-6 flex items-center">
                <input
                  id="same-as-shipping"
                  name="same-as-shipping"
                  type="checkbox"
                  checked=""
                  class="h-4 w-4 border-gray-300 rounded text-indigo-600 focus:ring-indigo-500"
                />
                <div class="ml-2">
                  <label
                    for="same-as-shipping"
                    class="text-sm font-medium text-gray-900"
                    >Desea que le llegue un correo electronico de
                    confirmación?</label
                  >
                </div>
              </div>
            </div>

            <div class="mt-10 flex justify-end pt-6 border-t border-gray-200">
              <button
                type="submit"
                class="bg-indigo-600 border border-transparent rounded-md shadow-sm py-2 px-4 text-sm font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-50 focus:ring-indigo-500"
              >
                Pagar ahora
              </button>
            </div>
          </div>
        </form>
      </section>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from "vue";
import {
  // eslint-disable-next-line no-unused-vars
  BellIcon,
  // eslint-disable-next-line no-unused-vars
  LightningBoltIcon,
  // eslint-disable-next-line no-unused-vars
  PhoneIcon,
  // eslint-disable-next-line no-unused-vars
  FireIcon,
  // eslint-disable-next-line no-unused-vars
  MenuIcon,
  // eslint-disable-next-line no-unused-vars
  TrashIcon,
  // eslint-disable-next-line no-unused-vars
  XIcon,
} from "@heroicons/vue/outline";
const props = defineProps({
  closeModal: Function,
  currentInvoice: Object,
});

const payNow = () => {
  alert("Pago Registrado")
}
</script>
