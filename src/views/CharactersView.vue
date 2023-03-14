<template>
  <div>
 <all-characters />
  </div>
</template>

<script>
import AllCharacters from '@/components/AllCharacters.vue';

export default {
  name: 'CharactersView',
  components: {
    AllCharacters
  },
}
</script>