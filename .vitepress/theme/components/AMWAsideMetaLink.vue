<script setup lang="ts">
export interface Links {
  id: string
  baseUrl: string
  anchor: string
  target: string
  style: string
}

defineProps<{
  links: Links[]
}>()
</script>

<template>
  <div>
    <template v-for="link in links">
      <a
        :href="(link.baseUrl ?? '') + link.id"
        :target="link.target"
        class="btn"
        :style="link.style"
        >{{ link.anchor }}</a
      >
    </template>
  </div>
</template>

<style scoped>
.btn {
  padding: 8px 24px;
  text-align: center;
  text-decoration: none;
  transition: all 0.5s ease-in-out;
  display: grid;
  background-color: var(--agw-btn-bg);
  color: var(--agw-btn-color);
  font-weight: 700;
}

.btn:hover {
  background-color: var(--agw-btn-hover-bg);
  color: var(--agw-btn-hover-color);
}
</style>
