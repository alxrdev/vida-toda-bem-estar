<template>
  <button
    :type="type"
    :class="['btn', { 'btn--block': isBlock, 'btn--rounded': isRounded }]"
    @click="onClick"
  >
    <slot />
  </button>
</template>

<script>
export default {
  name: 'BaseButton',
  props: {
    type: {
      type: String,
      required: false,
      default: 'button',
      validation: function (value) {
        return ['button', 'submit'].indexOf(value) !== -1
      }
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
    onClick: {
      type: Function,
      required: false,
      default: () => {}
    }
  }
}
</script>

<style scoped>
.btn {
  padding: .45rem 1.5rem;

  background: var(--orange);
  color: var(--white);

  font-size: 1rem;
  font-weight: 700;
  text-decoration: none;

  border: none;

  transition: background ease 0.3s;
  cursor: pointer;
}

.btn:hover {
  background: #f19220;
}

.btn--rounded {
  border-radius: 1.5rem;
}

.btn--block {
  display: block;
  width: 100%;
}
</style>