<template>
  <a :href="linkedinLink" class="channel-link" target="_blank">
    <span class="channel-icon Linkedin" aria-hidden="true">
      <icon type="linkedin" color="#fff" />
    </span>
    <span class="visually-hidden">{{ a11y }}</span>
  </a>
</template>

<script>
import Icon from '../../icons'
import { addQueryParameter } from '@podlove/utils/url'

const LINK = 'https://www.linkedin.com/shareArticle'

export default {
  components: {
    Icon
  },
  props: {
    text: {
      type: String,
      default: ''
    },
    subject: {
      type: String,
      default: ''
    },
    a11y: {
      type: String,
      default: ''
    }
  },
  computed: {
    linkedinLink() {
      return addQueryParameter(LINK, { url: this.link, mini: true, summary: this.text })
    }
  }
}
</script>

<style lang="scss">
@import 'channel';

.channel-icon.Linkedin {
  background-color: $channel-linkedin-color;
}
</style>
