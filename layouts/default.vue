<template>
  <div>
    <TheHeader />
    <main class="lg:block relative pt-16 lg:pt-24">
      <Nuxt />
    </main>
    <TheFooter />
    <TheMobileBottomNav />
  </div>
</template>

<script>
export default {
  head() {
    let canonical = `https://nuxtjs.org${this.$route.path}`
    if (this.$store.state.locale !== 'en') {
      canonical = `https://${this.$store.state.locale}.nuxtjs.org${this.$route.path}`
    }
    const link = [
      { rel: 'canonical', href: canonical },
      {
        rel: 'alternate',
        hreflang: 'en',
        href: `https://nuxtjs.org${this.$route.path}`
      }
    ]
    link.forEach(l => {
      if (l.href.slice(-1) !== '/') {
        l.href = l.href + '/'
      }
    })
    return {
      htmlAttrs: { lang: this.$store.state.locale },
      link,
      meta: [
        // Open Graph
        { hid: 'og:site_name', property: 'og:site_name', content: 'NuxtJS' },
        {
          hid: 'og:title',
          property: 'og:title',
          content: this.$store.state.lang.homepage.meta.title
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: this.$store.state.lang.homepage.meta.description
        },
        { hid: 'og:type', property: 'og:type', content: 'website' },
        { hid: 'og:url', property: 'og:url', content: canonical },
        {
          hid: 'og:image',
          property: 'og:image',
          content: 'https://grocery.litekart.in/images/social/codecanyon-99.png'
        },
        // Twitter Card
        {
          hid: 'twitter:card',
          name: 'twitter:card',
          content: 'summary_large_image'
        },
        { hid: 'twitter:site', name: 'twitter:site', content: '@nuxt_js' },
        {
          hid: 'twitter:title',
          name: 'twitter:title',
          content: this.$store.state.lang.homepage.meta.title
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: this.$store.state.lang.homepage.meta.description
        },
        {
          hid: 'twitter:image',
          name: 'twitter:image',
          content: 'https://grocery.litekart.in/images/social/codecanyon-99.png'
        },
        {
          hid: 'twitter:image:alt',
          name: 'twitter:image:alt',
          content: 'The NuxtJS Framework'
        }
      ]
    }
  }
}
</script>
