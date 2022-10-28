<template>
  <div class="w-full">
    <div class="head p-5 bg-white special-round">
      <nuxt-link :to="'/schedule/' + hari">
        <p class="day font-semibold text-2xl" :data-cy="'card-title-' + hari">
          {{ hari }}
        </p>
        <p class="desc text-pink-400" :data-cy="'card-desc-' + hari">
          {{ jumlahmatkul }} Mata Kuliah
        </p>
      </nuxt-link>
    </div>
    <div class="body p-2 bg-white mt-5 special-round">
      <div class="item p-3 bg-slate-100 mb-1">Statistik</div>
      <div class="item p-3 bg-slate-100 mb-1">Statistik</div>
      <div class="item p-3 bg-slate-100 mb-1">Statistik</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["hari", "jumlahmatkul"],
};
</script>

<style>
.special-round {
  @apply rounded-lg shadow-lg shadow-pink-200;
}
</style>
