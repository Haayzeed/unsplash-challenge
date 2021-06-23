<template>
  <div class="home">
    <sidebar/>
    <main-content />
  </div>
</template>

<script>
// @ is an alias to /src
import sidebar from '@/components/sidebar.vue'
import mainContent from '@/components/mainContent.vue'
export default {
  name: 'Home',
  components: {
    sidebar,
    mainContent
  },
  data(){
    return{
    }
  }
}
</script>
