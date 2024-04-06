<template>
    <!-- <h3 style="min-height: 100vh;">index</h3> -->
    <MainPageInfoSection/>
    <MainPagePromoSection/>
    <MainPageTilesSection />
</template>

<script>
import MainPageInfoSection from '../components/MainPage/InfoSection'
import MainPageTilesSection from '../components/MainPage/TilesSection'
import MainPagePromoSection from '../components/MainPage/PromoSection'
export default {
  components: {
    MainPageInfoSection,
    MainPageTilesSection,
    MainPagePromoSection,
  }
}
</script>