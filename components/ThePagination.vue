<template>
  <div class="bg-white px-4 sm:px-6 lg:px-8 mb-14">
    <div
      class="
        relative
        max-w-lg
        mx-auto
        lg:max-w-7xl
        border-t border-grey-200
        flex
        items-center
        justify-between
      "
    >
      <div class="-mt-px w-0 flex-1 flex">
        <NuxtLink
          v-if="!isFirstPage"
          :to="prevPage"
          class="
            border-t-2 border-transparent
            pt-4
            pr-1
            inline-flex
            items-center
            text-sm
            font-medium
            text-gray-500
            hover:text-purple-700 hover:border-purple-300
          "
        >
          <svg
            class="mr-3 h-5 w-5 text-gray-400"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 20 20"
            fill="currentColor"
            aria-hidden="true"
          >
            <path
              fill-rule="evenodd"
              d="M7.707 14.707a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 1.414L5.414 9H17a1 1 0 110 2H5.414l2.293 2.293a1 1 0 010 1.414z"
              clip-rule="evenodd"
            />
          </svg>
          Anterior
        </NuxtLink>
      </div>

      <div class="-mt-px w-0 flex-1 flex justify-end">
        <NuxtLink
          v-if="!isLastPage"
          :to="nextPage"
          class="
            border-t-2 border-transparent
            pt-4
            pl-1
            inline-flex
            items-center
            text-sm
            font-medium
            text-gray-500
            hover:text-purple-700 hover:border-purple-300
          "
        >
          Siguiente
          <svg
            class="ml-3 h-5 w-5 text-gray-400"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 20 20"
            fill="currentColor"
            aria-hidden="true"
          >
            <path
              fill-rule="evenodd"
              d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z"
              clip-rule="evenodd"
            />
          </svg>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    currentPage: {
      type: Number,
      required: true,
    },
    lastPage: {
      type: Number,
      required: true,
    },
  },
  computed: {
    prevPage() {
      return `/blog/page/${this.currentPage - 1}`
    },
    nextPage() {
      return `/blog/page/${this.currentPage + 1}`
    },
    isFirstPage() {
      return this.currentPage === 1
    },
    isLastPage() {
      return this.currentPage === this.lastPage
    },
  },
}
</script>
