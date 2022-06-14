<template>
  <div class="w-full h-screen absolute top-0 bg-gray-500/50">
    <div class="mx-auto max-w-2xl bg-white pt-10">
      <section
        aria-labelledby="payment-and-shipping-heading"
        class="py-16 lg:max-w-lg lg:w-full lg:mx-auto lg:pt-0 lg:pb-24 lg:row-start-1 lg:col-start-1"
      >
        <span
          class="cursor-pointer font-bold text-lg"
          @click="props.openModalPayment(false)"
        >
          X
        </span>
        <h2 id="payment-and-shipping-heading" class="sr-only">
          Detalles de pago
        </h2>
        <div>
          <h3
            id="contact-info-heading"
            class="text-lg font-medium text-gray-900"
          >
            Listado de Pagos Realizados
          </h3>
          <div class="flow-root mt-6">
            <ul role="list" class="-my-5 divide-y divide-gray-200">
              <li
                v-for="announcement in props.announcements"
                :key="announcement.id"
                class="py-5"
              >
                <div
                  class="relative rounded-lg p-3 focus-within:ring-2 focus-within:ring-cyan-500"
                >
                  <h3 class="text-sm font-semibold text-gray-800">
                    <a
                      :href="announcement.href"
                      class="hover:underline focus:outline-none"
                    >
                      <!-- Extend touch target to entire panel -->
                      <span class="absolute inset-0" aria-hidden="true" />
                      {{ announcement.title }}
                    </a>
                  </h3>
                  <p class="mt-1 text-sm text-gray-600 line-clamp-2">
                    {{ announcement.preview }}
                  </p>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from "vue";
const props = defineProps({
  openModalPayment: Function,
  announcements: Array
});
</script>
