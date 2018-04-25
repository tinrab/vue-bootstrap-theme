<template>
  <button type="button" :class="className">
    <slot />
  </button>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'nuxt-property-decorator';

@Component
export default class extends Vue {
  @Prop({ default: 'primary' })
  variant: string;
  @Prop() size?: string;
  @Prop() outline?: boolean;

  get className(): string {
    let name = 'button';
    name += ' button--' + (this.outline ? 'outline-' : '') + this.variant;
    if (this.size) {
      name += ' button--' + this.size;
    }
    return name;
  }
}
</script>

