<template>
  <div class="w-full min-w-[230px] relative">
    <div
      @click="isOpen = !isOpen"
      class="w-full bg-white flex justify-between items-center gap-3 cursor-pointer px-4 py-2.5 rounded-lg"
      :class="{ 'ring-[2px] ring-[#001827]': isOpen }"
    >
      <div class="flex gap-2 items-center">
        <div class="bg-[#A5A5A5] w-5 h-5 rounded-full"></div>
        <span class="text-[#001827] text-sm font-medium">{{ title }}</span>
      </div>
      <div>
        <svg
          width="10"
          height="6"
          viewBox="0 0 10 6"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M9 1L5 5L1 0.999999"
            stroke="#001827"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </div>
    </div>

    <div
      v-if="isOpen"
      class="w-full absolute top-12 left-0 bg-white rounded-lg px-3 divide-y divide-[#00182726]"
    >
      <div
        class="py-3 flex justify-between items-center cursor-pointer"
        v-for="(option, index, key) in options"
        :key="key"
        @click="changeValue(option)"
      >
        <div class="flex items-center gap-2">
          <div class="w-5 h-5 rounded-full bg-[#A5A5A5]"></div>
          <span class="text-[#001827] text-sm font-medium">{{
            option.name
          }}</span>
        </div>
        <svg
          v-if="value == option.value"
          width="15"
          height="11"
          viewBox="0 0 15 11"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M4.49996 8.475L1.60829 5.58334C1.45248 5.42752 1.24115 5.33999 1.02079 5.33999C0.800437 5.33999 0.589107 5.42752 0.433292 5.58334C0.277477 5.73915 0.189941 5.95048 0.189941 6.17084C0.189941 6.27994 0.211432 6.38799 0.253186 6.48879C0.29494 6.58959 0.35614 6.68118 0.433292 6.75834L3.91663 10.2417C4.24163 10.5667 4.76663 10.5667 5.09163 10.2417L13.9083 1.425C14.0641 1.26919 14.1516 1.05786 14.1516 0.837503C14.1516 0.617148 14.0641 0.405818 13.9083 0.250003C13.7525 0.0941888 13.5411 0.00665283 13.3208 0.00665283C13.1004 0.00665283 12.8891 0.0941888 12.7333 0.250003L4.49996 8.475Z"
            fill="black"
          />
        </svg>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";

const props = defineProps(["options", "modelValue"]);

const emit = defineEmits(["update:modelValue"]);
const value = ref("");
const title = ref("");
const isOpen = ref(false);
watch(value, (val) => {
  emit("update:modelValue", val);
});

watch(
  () => props.modelValue,
  (val) => {
    value.value = val;
  },
  { immediate: true }
);

watch(
  () => props.modelValue,
  (val) => {
    value.value = val;
    const selectedOption = props.options.find((option) => option.value === val);
    if (selectedOption) {
      title.value = selectedOption.name;
    } else {
      title.value = "";
    }
  },
  { immediate: true }
);

const changeValue = (option) => {
  value.value = option.value;
  title.value = option.name;
  isOpen.value = false;
};
</script>
