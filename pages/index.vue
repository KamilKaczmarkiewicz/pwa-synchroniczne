<template>
    <h3 style="min-height: 100vh;">index</h3>
    <MainPagePromoSection/>
    <MainPageTilesSection />
</template>

<script>
import MainPageTilesSection from '../components/MainPage/TilesSection'
import MainPagePromoSection from '../components/MainPage/PromoSection'
export default {
  components: {
    MainPageTilesSection,
    MainPagePromoSection,
  }
}
</script>