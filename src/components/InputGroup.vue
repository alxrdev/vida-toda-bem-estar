<template>
  <div class="input-group">
    <label :for="id">{{ label }}</label>
    <input
      :type="type"
      :id="id"
      @input="$emit('update:modelValue', $event.target.value)"
      :required="required"
    />
  </div>
</template>

<script>
export default {
  name: 'InputGroup',
  props: {
    value: {
      type: String
    },
    id: {
      type: String,
      required: true
    },
    label: {
      type: String,
      required: true
    },
    type: {
      type: String,
      required: false,
      default: 'text'
    },
    required: {
      type: Boolean,
      required: false,
      default: true
    }
  }
}
</script>

<style scoped>
.input-group {
  margin-bottom: 8px;
}

.input-group:last-of-type {
  margin-bottom: 0px;
}

.input-group label {
  display: block;
  margin-bottom: 3px;

  font-weight: 700;
}

.input-group input {
  width: 100%;
  height: 35px;

  padding: 5px 10px;

  background: var(--blue-light);
  color: var(--white);

  border: none;
}
</style>