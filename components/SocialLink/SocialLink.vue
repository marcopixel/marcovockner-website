<template lang="pug">
li.social-link
  a(:href="href" target="_blank" rel="noopener")
    FontAwesomeIcon(v-if="icon" :icon="icon")
    span {{ label }}
</template>

<script lang="ts">
export default {
  name: "SocialLink",

  props: {
    href: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      required: true,
    },
    icon: {
      type: [String, Array],
      required: false,
      default: "",
    },
  },
}
</script>

<style lang="scss" scoped>
.social-link {
  color: lighten($color-text-primary, 10%);
  font-size: 1.2rem;
  letter-spacing: 0.03em;
  margin-right: 2rem;
  transition: 100ms transform;

  @include hover-focus-active() {
    color: #fff;
  }

  &:last-child {
    margin-right: 0;
  }

  a {
    color: inherit;
    display: flex;
    align-items: center;
  }

  span {
    font-weight: 400;
  }

  svg {
    margin-right: 1rem;
  }
}
</style>
