<template>
  <div class="container mx-auto px-4 mb-12">
    <section class="rounded py-6 sm:p-6">
      <h1
        class="text-3xl uppercase font-medium pt-10 pb-8 text-center"
        v-html="wordings.why.body"
      />
      <div class="flex flex-col lg:flex-row items-start justify-between">
        <div class="lg:w-1/3 px-4 py-8 lg:p-8 flex flex-col items-center">
          <ModularIllustration class="inline-block" />
          <h4 class="uppercase font-medium text-2xl py-8">
            {{ wordings.why_modular.attrs.title }}
          </h4>
          <p
            class="leading-loose text-light-onSurfaceSecondary dark:text-dark-onSurfaceSecondary"
            v-html="wordings.why_modular.body"
          />
        </div>
        <div class="lg:w-1/3 px-4 py-8 lg:p-8 flex flex-col items-center">
          <PerformantIllustration class="inline-block" />
          <h4 class="uppercase font-medium text-2xl py-8">
            {{ wordings.why_performant.attrs.title }}
          </h4>
          <p
            class="leading-loose text-light-onSurfaceSecondary dark:text-dark-onSurfaceSecondary"
            v-html="wordings.why_performant.body"
          />
        </div>
        <div class="lg:w-1/3 px-4 py-8 lg:p-8 flex flex-col items-center">
          <EnjoyableIllustration class="inline-block" />
          <h4 class="uppercase font-medium text-2xl py-8">
            {{ wordings.why_enjoyable.attrs.title }}
          </h4>
          <p
            class="leading-loose text-light-onSurfaceSecondary dark:text-dark-onSurfaceSecondary"
            v-html="wordings.why_enjoyable.body"
          />
        </div>
      </div>
      <!-- <div class="text-center">
        <AppButton
          href="https://template.nuxtjs.org"
          class="py-3 px-6 text-base"
        >
          <svg
            slot="icon"
            aria-label="CodeSandbox"
            class="inline-block h-5 -mt-1 mr-1 align-middle"
            viewBox="0 0 1024 1024"
          >
            <g fill="currentColor">
              <path
                d="M719 851V639.85L902 533.8v211.47L719 851M302.08 643.44l-179.91-104.3v208.6l179.91 104.83V643.44M511.98 275.8l182.96-106.17L512.06 63 328.44 169.99l183.54 105.8"
              />
            </g>
            <g
              fill="none"
              stroke="currentColor"
              stroke-width="80"
              stroke-miterlimit="10"
            >
              <path d="M899 287.83L509 513v450M122.17 289L511.5 513" />
              <path
                d="M121 739.08l389.92 223.96L901 738.34V288L511 62 121 289z"
              />
            </g>
          </svg>
          {{ buttonWording }}
        </AppButton>
      </div> -->
    </section>
  </div>
</template>

<script>
import PerformantIllustration from '@/assets/illustrations/performant.svg?inline'
import ModularIllustration from '@/assets/illustrations/modular.svg?inline'
import EnjoyableIllustration from '@/assets/illustrations/enjoyable.svg?inline'

export default {
  components: {
    PerformantIllustration,
    ModularIllustration,
    EnjoyableIllustration
  },
  data() {
    return {
      wordings: this.$store.state.homepage,
      buttonWording: this.$store.state.lang.homepage.why.try_nuxtjs_online
    }
  }
}
</script>
