<template>
  <footer class="z-10 relative pb-16 lg:pb-0 lg:block">
    <!-- <NewsletterForm /> -->
    <div
      class="bg-light-elevatedSurface dark:bg-dark-elevatedSurface shadow-nuxt transition-colors duration-300 ease-linear"
    >
      <div class="container mx-auto px-4">
        <div
          class="flex flex-col sm:flex-row text-center sm:text-left items-center content-center justify-between pt-10 sm:py-10"
        >
          <nav
            v-for="(l, title, index) in links"
            :key="title"
            class="flex-1 w-full sm:w-auto mb-8 sm:mb-0"
            :class="{
              'sm:text-center': index === 1,
              'sm:text-right': index === 2
            }"
          >
            <h3
              class="font-bold uppercase text-light-onSurfacePrimary dark:text-dark-onSurfacePrimary text-lg pb-4 transition-colors duration-300 ease-linear"
            >
              {{ title }}
            </h3>
            <ul
              class="text-light-onSurfaceSecondary dark:text-dark-onSurfaceSecondary transition-colors duration-300 ease-linear"
            >
              <li v-for="(link, i) in l" :key="i" class="py-2">
                <a
                  v-if="link.href"
                  :href="link.href"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="hover:text-nuxt-lightgreen"
                >
                  {{ link.key }}
                </a>
                <NuxtLink
                  v-else
                  :to="link.to"
                  class="hover:text-nuxt-lightgreen"
                >
                  {{ link.key }}
                </NuxtLink>
              </li>
            </ul>
          </nav>
        </div>
      </div>
      <div
        class="lg:border-t border-light-border dark:border-dark-border transition-colors duration-300 ease-linear"
      >
        <div
          class="container mx-auto px-4 flex flex-row items-center content-center justify-between py-4 "
        >
          <div class="flex-1 flex">
            <DarkModeToggle />
          </div>
          <div class="flex-1 text-center hidden sm:block">
            <a
              class="block"
              href="/"
              @click.prevent="$router.push('/')"
              @click.right.stop.prevent="$router.push('/design')"
            >
              <h1 class="m-0 h-0 w-0 overflow-hidden">NUXTJS</h1>
              <SmallNuxtLogo
                class="inline-block h-6 lg:h-auto text-light-onSurfacePrimary dark:text-dark-onSurfacePrimary transition-colors duration-300 ease-linear"
              />
            </a>
          </div>
          <div class="flex-1 text-right">
            <!-- <AppSelect
              v-model="currentLang"
              :options="locales"
              label="Select language"
            >
              <template v-slot:icon>
                <GlobeIcon />
              </template>
            </AppSelect> -->
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import GlobeIcon from '@/assets/icons/globe.svg?inline'
import SmallNuxtLogo from '@/assets/images/logo-small.svg?inline'
import localeManager from '@/mixins/localeManager'

export default {
  components: {
    GlobeIcon,
    SmallNuxtLogo
  },
  mixins: [localeManager],
  data() {
    return {
      links: {
        discover: [
          // { key: 'Design resources', to: '/design' },
          { key: 'Blog', href: 'https://www.frontendfun.com/blog' },
          { key: 'Grocery Shop Demo', href: 'https://grocery.litekart.in' }
        ],
        follow: [
          {
            key: 'GitHub',
            href: 'https://github.com/itswadesh/sapper-ecommerce'
          },
          { key: 'Twitter', href: 'https://twitter.com/itswadesh' }
          // { key: 'Discord', href: 'https://discord.litekart.in' }
        ],
        support: [
          // { key: 'Sponsor NuxtJS', to: '/sponsor-nuxtjs' },
          { key: 'Report Issue', href: 'https://github.com/itswadesh/support' }
          // { key: 'NuxtJS Consulting', to: '/support' }
        ]
      }
    }
  }
}
</script>
