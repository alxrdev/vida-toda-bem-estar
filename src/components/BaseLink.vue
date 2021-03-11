<template>
  <a
    :class="['link', { 'link--btn': isButton, 'link--block': isBlock, 'link--rounded': isRounded }, `link--${size}`]"
    :href="href"
  >
    <slot />
  </a>
</template>

<script>
export default {
  name: 'BaseLink',
  props: {
    href: {
      type: String,
      required: false,
      default: '#'
    },
    isButton: {
      type: Boolean,
      required: false,
      default: false
    },
    isRounded: {
      type: Boolean,
      required: false,
      default: false
    },
    isBlock: {
      type: Boolean,
      required: false,
      default: false
    },
    size: {
      type: String,
      required: false,
      default: 'default',
      validate: function (value) {
        return ['default', 'large'].indexOf(value) !== -1
      }
    }
  }
}
</script>

<style scoped>
.link {
  color: var(--blue);
  text-decoration: none;
}

.link--btn {
  padding: .45rem 1.5rem;

  color: var(--white);
  background: var(--orange);

  font-size: 1rem;
  font-weight: 700;
  text-align: center;

  border: none;

  transition: background ease 0.3s;
  cursor: pointer;
}

.link--btn:hover {
  background: var(--orange-dark);
}

.link--rounded {
  border-radius: 1.5rem;
}

.link--block {
  display: block;
  width: 100%;
}

.link--large {
  padding: 1.3rem 1rem;

  font-size: 1.2rem;
}

@media (max-width: 768px) {
  .link--large {
    font-size: 1rem;
  }
}
</style>