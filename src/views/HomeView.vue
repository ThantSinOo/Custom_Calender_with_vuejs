<template>
  <div class="home">
  
    <CalenderComponent/>
  </div>
</template>

<script>
// @ is an alias to /src
import CalenderComponent from '@/components/CalenderComponent.vue'

export default {
  name: 'HomeView',
  components: {
    CalenderComponent
  }
}
</script>
