<script setup lang="ts">
import { defineProps } from "vue";
import { Country } from "../models/country.model";

interface Props {
  country: Country;
}

defineProps<Props>();
</script>

<template>
  <div class="bg-slate-100">
  <div class="h-56 sm:h-36 border border-gray-300">
    <img
      class="h-56 sm:h-36 w-full"
      :src="country.flags.png"
      :alt="country.flags.alt"
    />
  </div>
  <h4 class="text-xl font-bold text-gray-600 pt-1">{{ country.name.common }}</h4>
  <p class="text-sm text-gray-500">
    Capital:
    <span v-for="capital in country.capital" class="font-bold">{{
      capital
    }}
    <template> </template>
    </span>
  </p>
  <p class="text-sm text-gray-500">
    Population:
    <span class="font-bold">{{ country.population?.toLocaleString() }}</span>
  </p>
  <p class="text-sm text-gray-500">
    Region:
    <span class="font-bold">{{ country.region }}</span>
  </p>
  </div>
</template>
