<template>
  <div>
    <div class="p-10">
      <h1 class="text-4xl font-bold">Candidates</h1>
    </div>
    <div
      class="
        p-10
        grid grid-cols-1
        sm:grid-cols-1
        md:grid-cols-3
        lg:grid-cols-3
        xl:grid-cols-3
        gap-5
      "
    >
      <div
        v-bind:key="candidate in candidates"
        class="rounded overflow-hidden shadow-lg"
      >
        <img class="w-full" src="/avatar.png" alt="" />
        <div class="px-6 py-4">
          <div class="font-bold text-xl mb-2">{{ candidate.name }}</div>
          <p class="text-gray-700 text-base">{{ candidate.description }}</p>
        </div>
        <div class="px-6 pt-4 pb-2">
          <span
            v-for-key="strength in JSON.parse(candidate.strengths)"
            class="
              inline-block
              bg-gray-200
              rounded-full
              px-3
              py-1
              text-sm
              font-semibold
              text-gray-700
              mr-2
              mb-2
            "
            >{{ strength }}</span
          >
        </div>
        <div class="p-6 float-right">
          <button-temp v-bind:id="candidate.id"></button-temp>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ButtonTemp from "./Button-temp.vue";
export default {
  components: { ButtonTemp },
  props: ["candidates"],
};
</script>
