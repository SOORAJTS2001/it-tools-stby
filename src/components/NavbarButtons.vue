<script setup lang="ts">
import { BrandGithub, BrandTwitter, InfoCircle, Moon, Sun } from '@vicons/tabler';
import { useStyleStore } from '@/stores/style.store';

const styleStore = useStyleStore();
const { isDarkTheme } = toRefs(styleStore);
</script>

<template>
  <c-tooltip tooltip="Github repository" position="bottom">
    <c-button
      circle
      variant="text"
      href="https://github.com/CorentinTh/it-tools"
      target="_blank"
      rel="noopener noreferrer"
      aria-label="IT-Tools' GitHub repository"
    >
      <n-icon size="25" :component="BrandGithub" />
    </c-button>
  </c-tooltip>

  <c-tooltip tooltip="Twitter account" position="bottom">
    <c-button
      circle
      variant="text"
      href="https://twitter.com/ittoolsdottech"
      rel="noopener"
      target="_blank"
      aria-label="IT Tools' Twitter account"
    >
      <n-icon size="25" :component="BrandTwitter" />
    </c-button>
  </c-tooltip>

  <c-tooltip tooltip="About IT-Tools" position="bottom">
    <c-button circle variant="text" to="/about" aria-label="About">
      <n-icon size="25" :component="InfoCircle" />
    </c-button>
  </c-tooltip>
  <c-tooltip :tooltip="isDarkTheme ? 'Light mode' : 'Dark mode'" position="bottom">
    <c-button circle variant="text" aria-label="Toggle dark/light mode" @click="() => styleStore.toggleDark()">
      <n-icon v-if="isDarkTheme" size="25" :component="Sun" />
      <n-icon v-else size="25" :component="Moon" />
    </c-button>
  </c-tooltip>
</template>

<style lang="less" scoped>
.n-button {
  &:not(:last-child) {
    margin-right: 5px;
  }
}
</style>
