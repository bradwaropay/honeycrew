<template>
  <div
    class="polaroid"
    @click="$emit('newBear')"
  >
    <div class="polaroid__image" />
    <div class="polaroid__tab">
      <h2 class="polaroid__info polaroid__info--name">
        {{ character.firstName }} "{{ character.nickName }}" {{ character.lastName }}
      </h2>
      <h3 class="polaroid__info polaroid__info--role">
        The {{ character.role }}
      </h3>
      <p class="polaroid__info polaroid__info--bear">
        {{ character.descriptor }} {{ character.type === 'Honey Badger' ? character.type : character.type + ' Bear' }}
      </p>
      <p class="polaroid__info polaroid__info--specialty">
        Specialty: {{ character.specialty }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    character: {
      type: Object,
      default: function() {
        return {}
      }
    }
  }
}
</script>

<style lang="postcss">
.polaroid {
  transform: rotate(2.5deg);
  width: 50vw;

  &__image {
    background-color: orange;
    border-bottom-width: 0;
    border-color: white;
    border-left-width: 2vw;
    border-style: solid;
    border-right-width: 2vw;
    border-top-width: 2vw;
    height: 45vw;
  }

  &__tab {
    background-color: white;
    color: black;
    padding: 2vw;
    text-align: center;
  }

  &__info {
    margin: 0;

    &--name,
    &--role {
      font-family: 'Chelsea Market', cursive;
    }

    &--name {
      font-size: 1.5rem;
    }

    &--role {
      color: orangered;
      font-size: 2rem;
    }

    &--bear {
      margin-top: 1rem;
    }
  }
}
</style>
