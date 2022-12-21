<script setup lang="ts">
import { ref, watch } from "vue";
import { NButton, ButtonProps } from "naive-ui";

type ButtonThemeOverrides = NonNullable<ButtonProps["themeOverrides"]>;
const buttonThemeOverrides: ButtonThemeOverrides = {
  heightMedium: "40px",
  textColor: "green",
  textColorHover: "red",
};

const button = ref<typeof NButton | null>(null);
watch(button, () => {
  console.log(button.value?.handleClick());
});

const handleClick = () => {
  alert("clicked");
};
</script>

<template>
  <div>
    <n-button
      ref="button"
      :theme-overrides="buttonThemeOverrides"
      size="medium"
      :on-click="handleClick"
      >Naive UI</n-button
    >
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
