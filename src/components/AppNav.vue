<template functional>
  <header class="header">
    <nav class="nav">
      <g-link class="nav__link" to="/">Home</g-link>
      <g-link class="nav__link" to="/about/">About</g-link>
    </nav>
  </header>
</template>

<script>
export default { name: "AppNav" };
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

.nav {
  display: flex;
  justify-content: center;
  width: 100%;
  &__link {
    padding: 20px;
    text-decoration: none;
    &:hover {
      text-decoration: underline;
    }
  }
}
</style>