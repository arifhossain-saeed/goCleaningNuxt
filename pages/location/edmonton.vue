<template>
  <section class="go-cleaning-page">
    <ThePageBannerSection :pageMaterials="bannerPageMaterials" />

    <TheQuoteRequestInfoSection />
  </section>
</template>

<script>
import ThePageBannerSection from "@/components/shared/ThePageBannerSection";
import TheQuoteRequestInfoSection from "@/components/shared/TheQuoteRequestInfoSection";
export default {
name: "calgary",
  components: {TheQuoteRequestInfoSection, ThePageBannerSection},

  data(){
    return {
      bannerPageMaterials: {
        bannerImage: '/img/go-cleaning-edmonton-banner-bg.png',
        pageTitle: 'Edmonton',
        pageSubtitle: 'Perfection is our passion',
        hasButton: false
      }
    }
  }
}
</script>

<style scoped>

</style>
