<template>

  <Header />
  <div class="container">
    <div class="row">
      <div class="col-md-6 mx-auto text-center">
        <img alt="Vue logo" src="./assets/logo.png">
        <h1>{{ message }}</h1>
      </div>
    </div>
    <Courses>
        <ol class="breadcrumb">
          <li class="breadcrumb-item"><a href="#">Home</a></li>
          <li class="breadcrumb-item active" aria-current="page">Library</li>
        </ol>
    </Courses>
  </div>
  <Footer url="https://www.yousfism.online" title="Soufiane Yousfi Mghari Portfolio" text="YousfiSM"/>
</template>

<script>

import Header from './components/Header';
import Courses from './components/Courses';
import Footer from './components/Footer';

export default {
  name: 'App',
  components : {
    Header,
    Courses,
    Footer
  },
  data(){
    return{
      message : "Yousfi SM"
    }
  },
  methods : {
    handleClick(){
      console.log(this.$refs.book.value);
      this.$refs.book.classList.add('active');
      this.$refs.book.focus();
    }
  }

}
</script>

<style>
  .container{
    margin-top: 60px;
  }
</style>
