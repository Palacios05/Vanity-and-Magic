<script setup>
import { useGenerateImageVariant } from '@/@core/composable/useGenerateImageVariant'
import miscMaskDark from '@images/misc/misc-mask-dark.png'
import miscMaskLight from '@images/misc/misc-mask-light.png'
import miscObj from '@images/pages/misc-under-maintenance-object.png'
import miscUnderMaintenance from '@images/pages/misc-under-maintenance.png'

const authThemeMask = useGenerateImageVariant(miscMaskLight, miscMaskDark)

definePage({
  meta: {
    layout: 'blank',
    public: false,
  },
})
</script>

<template>
  <div class="misc-wrapper">
    <div class="text-center mb-10">
      <!-- 👉 Title and subtitle -->
      <h4 class="text-h4 mb-2">
        Under Maintenance! 🚧
      </h4>
      <p class="text-body-1 mb-0">
        Sorry for the inconvenience but we're performing some maintenance at the moment
      </p>
    </div>

    <!-- 👉 Image -->
    <div class="misc-avatar w-100 text-center">
      <VImg
        :src="miscUnderMaintenance"
        :height="$vuetify.display.xs ? 400 : 500"
        alt="Coming Soon"
        class="my-sm-5"
      />

      <VBtn
        to="/"
        class="mt-10"
      >
        Back to Home
      </VBtn>

      <VImg
        :src="authThemeMask"
        class="d-none d-md-block footer-coming-soon flip-in-rtl"
        cover
      />

      <VImg
        :src="miscObj"
        class="d-none d-md-block footer-coming-soon-obj"
        :max-width="173"
        height="170"
      />
    </div>
  </div>
</template>

<style lang="scss">
@use "@core/scss/template/pages/misc.scss";
</style>
