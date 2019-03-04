<template>
  <polaroid
    :character="character"
    @newBear="generateBear()"
  />
</template>

<script>
import Names from '~/assets/names.json'
import Character from '~/assets/character.json'

import Polaroid from '~/components/Polaroid.vue'

export default {
  components: {
    Polaroid
  },
  data() {
    return {
      firstName: '',
      nickName: '',
      lastName: '',
      role: '',
      descriptor: '',
      type: '',
      specialty: '',
      hat: ''
    }
  },
  computed: {
    character: function() {
      return {
        firstName: this.firstName,
        nickName: this.nickName,
        lastName: this.lastName,
        role: this.role,
        descriptor: this.descriptor,
        type: this.type,
        specialty: this.specialty,
        hat: this.hat
      }
    }
  },
  methods: {
    generateBear: function() {
      function getRandom(array, filter) {
        return array[Math.floor(Math.random() * array.length)]
      }

      this.firstName = getRandom(Names.firstName)
      this.nickName = getRandom(Names.nickName)
      this.lastName = getRandom(Names.lastName)
      this.role = getRandom(Character.role)
      this.descriptor = getRandom(Character.descriptor)
      const bear = getRandom(Character.bear)
      this.type = bear.type
      this.specialty = bear.specialty
      this.hat = getRandom(Character.hat)
    }
  }
}
</script>
