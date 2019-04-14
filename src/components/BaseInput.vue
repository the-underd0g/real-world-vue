<template>
  <label v-if="label">{{ label }}</label>
  <input :value="value" @input="updateValue" v-bind="$attrs" v-on="listeners" />
</template>

<script>
import { formFieldMixin } from '../mixins/formFieldMixin'

export default {
  name: 'BaseInput',
  mixins: [formFieldMixin],
  computed: {
    listeners() {
      return {
        ...this.$listeners,
        input: this.updateValue
      }
    }
  }
}
</script>

<style scoped></style>
