<template>
  <section class="container">
    <h1>Buttons</h1>
    <div class="row">
      <template v-for="outline in [false, true]">
        <template v-for="variant in ['primary','secondary','success','danger', 'warning', 'info']">
          <div class="col-md-4 pb-2" v-for="size in ['', 'sm', 'lg']" :key="`${variant}_${outline}_${size}`">
            <ui-button :size="size" :variant="variant" :outline="outline">
              {{variant}} {{size}}
            </ui-button>
          </div>
        </template>
      </template>
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';

@Component
export default class extends Vue {}
</script>
