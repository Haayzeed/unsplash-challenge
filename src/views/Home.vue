<template>
  <div class="home">
    <sidebar/>
    <main-content :results="results" />
    <!-- {{searchImage}} -->
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
  props:{
      searchImage: String
  },
  data(){
    return{
      results: [],
    }
  },
  // methods:{
  //   loadImage(){
  //     axios.get('https://api.unsplash.com/search/photos?query=nature&client_id=RkUiv46QmqkuzRFjLJ7FhWdQOQiBLjYkYPO0GoVJ6tQ').then(response =>{
  //       this.results = response.data.results
  //       console.log(this.results)
  //     })
  //   },
  //   findImage(){
  //     axios.get('https://api.unsplash.com/search/photos?query=' +this.searchImage+'&client_id=RkUiv46QmqkuzRFjLJ7FhWdQOQiBLjYkYPO0GoVJ6tQ').then(response =>{
  //       this.results = response.data.results
  //       console.log(this.results)
  //     })
  //   }
  // },
  // created(){
  //   this.loadImage()
  // }
}
</script>
