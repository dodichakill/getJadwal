<template>
  <div>
    <button
      class="rounded-full mt-3 bg-pink-400 hover:bg-pink-500 active:bg-pink-600 text-white px-2 py-4 w-full font-bold"
      data-cy="btn-login"
    >
      {{ title }}
    </button>
  </div>
</template>

<script>
export default {
  props: ["title"],
  emits: ["function"],
};
</script>
