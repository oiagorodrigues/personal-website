<template>
  <div class="layout">
    <AppNav></AppNav>
    <main>
      <slot />
    </main>
  </div>
</template>

<script>
import { AppNav } from "~/components";
export default {
  name: "DefaultLayout",
  components: { AppNav }
};
</script>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
body {
  font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
}

.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}
</style>
