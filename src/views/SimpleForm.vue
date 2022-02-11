<template>
  <div>
    <h1>Create an event</h1>
    <form @submit.prevent="sendForm">

      <BaseSelect
        :options="categories"
        v-model="event.category"
        label="Select a category"
      />

      <h3>Name & describe your event</h3>

      <BaseInput
        v-model="event.title"
        label="Title"
        type="text"
      />

      <BaseInput
        v-model="event.description"
        label="Description"
        type="text"
      />
      <h3>Where is your event?</h3>

      <BaseInput
        v-model="event.location"
        label="Location"
        type="text"
      />

      <BaseRadioGroup
        legend="Are pets allowed?"
        v-model="event.pets"
        name="pets"
        :options="petOptions"
      />

      <h3>Extras</h3>

      <BaseCheckbox
        v-model="event.extras.catering"
        label="Catering"
      />

      <BaseCheckbox
        v-model="event.extras.music"
        label="Live music"
      />

      <button class="button -fill-gradient" type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios'
import BaseInput from '../components/BaseInput.vue'
import BaseSelect from '../components/BaseSelect.vue'
import BaseRadioGroup from '../components/BaseRadioGroup.vue'
export default {
  data () {
    return {
      categories: [
        'sustainability',
        'nature',
        'animal welfare',
        'housing',
        'education',
        'food',
        'community'
      ],
      event: {
        category: '',
        title: '',
        description: '',
        location: '',
        pets: 1,
        extras: {
          catering: false,
          music: false
        }
      },
      petOptions: [
        { label: 'Yes', value: 1 },
        { label: 'No', value: 0 }
      ]
    }
  },
  methods: {
    sendForm () {
      // We will handle form submition here
    }
  },
  components: { BaseInput, BaseSelect, BaseRadioGroup }
}
</script>
