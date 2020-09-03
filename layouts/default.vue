<template>
  <div class="layout">
    <hc-header />

    <div>
      <nuxt/>
    </div>

    <hc-footer v-bind="{ year: new Date().getFullYear(), company: 'Вайтлейбл' }" />
  </div>
</template>

<script>
import Header from '@/components/common/Header'
import Footer from '@/components/common/Footer'

export default {
  components: {
    hcHeader: Header,
    hcFooter: Footer
  }
}
</script>


<style lang="scss" scoped>
.layout {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.main {
  background: #f6f6f6;
  min-height: calc(100vh - 505px);
  height: 100%;
}
</style>
