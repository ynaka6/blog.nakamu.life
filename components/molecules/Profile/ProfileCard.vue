<template>
  <div class="border bg-white shadow-sm p-2 md:px-4">
    <h3 class="text-2xl">Profile</h3>
    <div>
      <picture class="p-6 block w-48 h-48 mx-auto rounded-full">
        <source
          type="image/webp"
          :srcset="`${author.fields.image.fields.file.url}?fm=webp`"
        />
        <n-image
          :alt="author.fields.name"
          :src="`${author.fields.image.fields.file.url}`"
          class="rounded-full"
        />
      </picture>
      <p class="text-center">
        <n-link
          v-if="author.fields.url"
          :to="author.fields.url"
          class="text-blue-600 hover:text-blue-300 no-underline hover:underline"
          :target-blank="true"
        >
          {{ author.fields.name }}
        </n-link>
        <span v-else>
          {{ author.fields.name }}
        </span>
      </p>
      <p class="py-4 text-gray-800" v-text="author.fields.shortBio"></p>
      <div class="py-2 flex">
        <a
          v-if="author.fields.twitter"
          :href="'https://twitter.com/' + author.fields.twitter"
          target="_blank"
          style="color: #55acee;"
          rel="noreferrer"
          aria-label="Twitter"
          class="mr-1"
        >
          <n-icon icon="twitter" class="w-6 h-6" />
        </a>
        <a
          v-if="author.fields.github"
          :href="'https://github.com/' + author.fields.github"
          target="_blank"
          style="color: #333;"
          rel="noreferrer"
          aria-label="Github"
          class="mr-1"
        >
          <n-icon icon="github" class="w-6 h-6" />
        </a>
        <a
          v-if="author.fields.gitlab"
          :href="'https://gitlab.com/' + author.fields.gitlab"
          target="_blank"
          style="color: #fa6d34;"
          rel="noreferrer"
          aria-label="Gitlab"
          class="mr-1"
        >
          <n-icon icon="gitlab" class="w-6 h-6" />
        </a>
        <a
          v-if="author.fields.instagram"
          :href="'https://www.instagram.com/' + author.fields.instagram"
          target="_blank"
          style="color: #d93177;"
          rel="noreferrer"
          aria-label="instagram"
        >
          <n-icon icon="instagram" class="w-6 h-6" />
        </a>
      </div>
      <p v-if="author.fields.url" class="py-2 text-right">
        <n-link
          :to="author.fields.url"
          class="text-blue-600 hover:text-blue-300 no-underline hover:underline"
          :target-blank="true"
        >
          プロフィール詳細はこちら
        </n-link>
      </p>
    </div>
  </div>
</template>

<script>
import NLink from '~/components/atoms/links/NLink'
import NIcon from '~/components/atoms/NIcon'
import NImage from '~/components/atoms/NImage'

export default {
  components: { NLink, NIcon, NImage },
  props: {
    author: { type: Object, required: true }
  }
}
</script>

<style scoped lang="postcss"></style>
