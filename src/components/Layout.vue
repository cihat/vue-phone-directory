<template>
  <div class="layoutContainer">
    <div class="layoutContainer_header">
      {{ header }}
    </div>
    <div class="layoutContainer_headerBar">
      <HeaderBar
        :show-back-button="showBackButton"
        :show-search-bar="showSearchBar"
        :on-search-change="onSearchChange"
      />
    </div>
    <slot />
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
// @ts-ignore
import HeaderBar from "./HeaderBar.vue";

interface ILayoutProps {
  header: string;
  showBackButton?: boolean;
  showSearchBar?: boolean;
  onSearchChange?: (e?: Event) => void;
}
defineProps<ILayoutProps>();
</script>

<style lang="scss">
@import "../styles/base/colors.scss";
.layoutContainer {
  display: flex;
  flex-direction: column;
  max-width: 1396px;
  margin: 0 auto;
  overflow-x: hidden;

  & .layoutContainer_header {
    border: 2px solid var(--lightgray);
    padding: 1rem;
    font-size: var(--h2);
    background: var(--lightgray);
  }
}
</style>
