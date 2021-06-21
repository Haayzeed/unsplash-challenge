<template>
    <div>
        <div class="main-content">
            <header>
                <div class="menu-toggle">
                    <label for="sidebar-toggle">
                        <span class="fas fa-bars"></span>
                    </label>
                </div>
                <div class="input-box">
                    <form action="" @submit.prevent="findImage">
                        <input type="text" class="input-large" placeholder="Find something" v-model="searchImage">
                        <button>Search</button>
                    </form>
                </div>
                <div class="header-icons">
                    <span class="fas fa-bell"></span>
                    <span><img src="@/assets/img.png" alt="" class="avatar"></span>
                    <span class="">Abigail <i class="fas fa-caret-down"></i></span>
                </div>
            </header>
            <main>
                <div class="page-header">
                    <form action="">
                        <select name="" id="">
                            <option value="">World</option>
                        </select>
                        <select name="" id="">
                            <option value="">Following</option>
                        </select>
                        <select name="" id="">
                            <option value="">Popular</option>
                        </select>
                        <select name="" id="">
                            <option value="">Post</option>
                        </select>
                        <select name="" id="">
                            <option value="">Gender</option>
                        </select>
                        <select name="" id="">
                            <option value="">Location</option>
                        </select>
                        <select name="" id="">
                            <option value="">Profession</option>
                        </select>
                        <select name="" id="">
                            <option value="">Community</option>
                        </select>
                    </form>
                </div>
                <div class="content" v-if="results">
                    <div class="card"  v-for="(result, index) in results" :key="index">
                        <img :src="result.urls.regular" alt="" lazy>
                    </div>
                </div>
            </main>
        </div>

    </div>
</template>
<script>

import axios from 'axios'
export default{
    data(){
        return{
            results: [],
            searchImage: ''
        }
    },
    methods:{
    loadImage(){
      axios.get('https://api.unsplash.com/search/photos?query=nature&client_id=RkUiv46QmqkuzRFjLJ7FhWdQOQiBLjYkYPO0GoVJ6tQ').then(response =>{
        this.results = response.data.results
        console.log(this.results)
      })
    },
    findImage(){
      axios.get('https://api.unsplash.com/search/photos?query=' +this.searchImage+'&client_id=RkUiv46QmqkuzRFjLJ7FhWdQOQiBLjYkYPO0GoVJ6tQ').then(response =>{
        this.results = response.data.results
        console.log(this.results)
      })
    }
  },
  created(){
    this.loadImage()
  }
}
</script>


<style lang="scss">
    #sidebar-toggle{
        &:checked ~ .body-label{
            right: 0;
        }
        &:checked ~ .main-content{
            margin-left: 0%;
        }
    }
    .main-content{
        margin-left: 280px;
        transition: margin-left 300ms;
        @media (max-width: 1124px){
            margin-left: 0;
        }
        main{
            padding: 1rem 2.5rem;
            background: var(--light-gray);
            min-height: calc(100vh - 70px);
            margin-top: 70px;
            .page-header{
                display: flex;
                margin-bottom: 20px;
                form{
                    width: 100%;
                    display: flex;
                    select{
                        width: 100%;
                        padding: 10px;
                        border: none;
                        border-right: 1px solid #ccc;
                    }
                }
            }
            .content{
                display: grid;
                grid-template-columns: repeat(4, 1fr);
                grid-column-gap: 30px;
                @media (max-width: 1124px){
                    grid-template-columns: repeat(4, 1fr);
                }
                @media (max-width: 600px){
                    grid-template-columns: repeat(2, 1fr);
                }
                @media (min-width: 601px) and (max-width: 768px){
                    grid-template-columns: repeat(3, 1fr);
                }
                .card{
                    height: 250px;
                    margin-bottom: 30px;
                    img{
                        width: 100%;
                        height: 100%;
                    }
                }
            }
        }
    }
</style>