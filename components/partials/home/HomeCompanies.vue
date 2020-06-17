<template>
  <div
    class="bg-light-elevatedSurface dark:bg-dark-elevatedSurface shadow-nuxt"
  >
    <div class="container mx-auto px-4 py-24 md:mb-8">
      <section>
        <h1 class="text-3xl font-medium uppercase text-center pb-8">Videos</h1>
        <ClientOnly>
          <div class="flex flex-col lg:flex-row items-center justify-between">
            <div class="p-4 lg:p-8 text-center">
              <a
                href="https://grocery.litekart.in/"
                target="_blank"
                rel="noopener nofollow"
                class="company relative block"
              >
                <img
                  src="https://raw.githubusercontent.com/itswadesh/litekart-docs-md/master/videos/litekart-graocery-store-front.gif"
                  alt="Store Front"
                  :class="[
                    $colorMode.value === 'dark'
                      ? 'absolute top-0 left-0 opacity-0'
                      : ''
                  ]"
                  class="original"
                />
              </a>
            </div>
            <div class="p-4 lg:p-8 text-center">
              <a
                href="https://vendor.litekart.in/"
                target="_blank"
                rel="noopener nofollow"
                class="company relative block"
              >
                <img
                  src="https://raw.githubusercontent.com/itswadesh/litekart-docs-md/master/videos/litekart-graocery-vendor.gif"
                  alt="Vendor APP"
                  :class="[
                    $colorMode.value === 'dark'
                      ? 'absolute top-0 left-0 opacity-0'
                      : ''
                  ]"
                  class="original"
                />
              </a>
            </div>
            <div class="p-4 lg:p-8 text-center">
              <a
                href="https://delivery.litekart.in/"
                target="_blank"
                rel="noopener nofollow"
                class="company relative block"
              >
                <img
                  src="https://raw.githubusercontent.com/itswadesh/litekart-docs-md/master/videos/litekart-graocery-delivery.gif"
                  alt="Delivery Panel"
                  :class="[
                    $colorMode.value === 'dark'
                      ? 'absolute top-0 left-0 opacity-0'
                      : ''
                  ]"
                  class="original"
                />
              </a>
            </div>
            <div class="p-4 lg:p-8 text-center">
              <a
                href="https://gadmin.litekart.in/"
                target="_blank"
                rel="noopener nofollow"
                class="company relative block"
              >
                <img
                  src="https://raw.githubusercontent.com/itswadesh/litekart-docs-md/master/videos/litekart-graocery-admin.gif"
                  alt="Admin Panel"
                  :class="[
                    $colorMode.value === 'dark'
                      ? 'absolute top-0 left-0 opacity-0'
                      : ''
                  ]"
                  class="original"
                />
              </a>
            </div>
          </div>
        </ClientOnly>
      </section>
    </div>
  </div>
</template>

<script></script>

<style lang="scss" scoped>
.company {
  .preview {
    opacity: 0.5;
    filter: grayscale(100%);
    transition: all 250ms ease;
  }
  .original {
    opacity: 0.5;
    filter: grayscale(100%);
    transition: all 250ms ease;
  }
  &:hover {
    .preview {
      opacity: 0;
    }
    .original {
      filter: grayscale(0%);
      opacity: 1;
    }
  }
}
</style>
