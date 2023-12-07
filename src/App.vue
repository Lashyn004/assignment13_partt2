<template>
  <div id="app" class="p-4">
    <app-accordion v-for="(item, index) in accordionItems" :key="index" class="mb-4">
      <template v-slot:title>
        <span class="font-semibold text-lg">{{ item.title }}</span>
      </template>
      <template v-slot:content>
        <p class="text-gray-700">
          <b>Lorem</b>, ipsum dolor sit amet consectetur adipisicing elit. Quia,
          porro. Non a excepturi, voluptatibus ipsam magnam, eligendi,
          accusantium ipsa quae quis praesentium voluptate saepe ullam sint ea
          itaque consectetur impedit?
        </p>
      </template>
    </app-accordion>
  </div>
</template>

<script>
import AppAccordion from "/Users/lashynnnsh004/Desktop/Assignment133/part2/src/components/AppAccordion.vue";

export default {
  name: "App",
  components: {
    AppAccordion,
  },
  data() {
    return {
      accordionItems: [
        { title: "Accordion 1" },
        { title: "Accordion 2" },
        // Add more items as needed
      ],
    };
  },
};
</script>

<style>
/* You can keep your existing styles or add more styles here */

/* Add a bit of spacing between accordions */
.app-accordion + .app-accordion {
  margin-top: 10px;
}
</style>
