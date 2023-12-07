<template>
  <div>
    <button
      @click="toggleAccordion"
      class="flex items-center space-x-3 focus:outline-none"
      :aria-expanded="isOpen"
      :aria-controls="`collapse${_uid}`"
    >
      <div class="flex items-center space-x-2">
        <slot name="title" />
      </div>
      <svg
        class="w-4 transform transition-transform duration-300"
        :class="{ 'rotate-180': isOpen }"
        fill="none"
        stroke="currentColor"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 16 10"
        aria-hidden="true"
      >
        <path
          d="M15 1.2l-7 7-7-7"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </button>

    <transition name="fade">
      <div
        v-show="isOpen"
        :id="`collapse${_uid}`"
        class="mt-2 p-3 bg-white border border-gray-300 rounded-md shadow-md transition-all duration-300"
      >
        <slot name="content" />
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },

  methods: {
    toggleAccordion() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>
