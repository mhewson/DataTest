<template>
  <fieldset>
    <legend> {{ legend }}</legend>
    <component
      v-for="option in options"
      :key="option.value"
      :is="displayBlock ? 'div' : 'span'"
      :class="{
        inline: !displayBlock
      }
      "
    >
      <BaseRadio
        :label="option.label"
        :value="option.value"
        :name="name"
        :modelValue="modelValue"
        @update:modelValue="$emit('update:modelValue', $event)"
      />
    </component>
  </fieldset>
</template>

<script>
export default {
  props: {
    legend: {
      type: String,
      required: true
    },
    options: {
      type: Array,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    modelValue: {
      type: [String, Number],
      required: true
    },
    displayBlock: {
      type: Boolean,
      required: true
    }
  }
}
</script>

<style>
.inline {
  margin-right: 20px;
}
</style>
