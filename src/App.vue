<template>
  <div id="main-wrapper">
    <DefaultLayout>
      <transition name="fade" appear>
        <main>
          <router-view />
        </main>
      </transition>
    </DefaultLayout>
  </div>
</template>

<static-query>
query App {
  metadata {
    siteName
    siteDescription
  }
}
</static-query>

<script>
export default {
  name: "App",
  metaInfo() {
    return {
      title: this.$static.metadata.siteName,
      meta: [
        {
          key: "description",
          name: "description",
          content: this.$static.metadata.siteDescription
        }
      ]
    };
  }
};
</script>

<style>
.fade-enter-active {
  transition: opacity 0.5s;
}

.fade-enter {
  opacity: 0;
}
</style>