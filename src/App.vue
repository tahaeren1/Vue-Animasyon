<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6 col-md-offset-3">
        <h3>Animation ve Transition</h3>
        <hr>
        <button class="btn btn-primary" @click="show = !show">Kutuyu Göster/Gizle</button>
        <br><br>
        <transition name="fade">
          <div class="alert alert-success" v-show="show">Bu bir Alert kutusudur</div>
        </transition>
          <hr>
          <br><br>
          <transition name="slide" type="animation">
            <div class="alert alert-warning" v-show="show">Bu bir Alert kutusudur</div>
        </transition>
        <hr>
        <transition
                enter-class=""
                enter-active-class="animated shake"
                leave-class=""
                leave-active-class="animated swing"
                name="slide" type="animation">
          <div class="alert alert-warning" v-show="show">Bu bir Alert kutusudur</div>
        </transition>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show : false
    }
  }

}
</script>

<style>
  .fade-enter {
    opacity: 0;

  }
  .fade-enter-active {
    transition: opacity 1s;


  }
  .fade-leave {


  }
  .fade-leave-active {
    transition: opacity 1s;
    opacity: 0;

  }
  .slide-enter{
    opacity: 0;


  }
  .slide-enter-active{
    animation: slide-in 1s ease-out forwards;
    transition: opacity 0.5s;
  }
  .slide-leave{

  }
  .slide-leave-active{
    animation: slide-out 1s ease-out forwards;
    transition: opacity 3s;
    opacity: 0;

  }
  @keyframes slide-in {
    from {
transform: translateY(20px);
    }
    to {
 transform: translateY(0px);
    }
    
  }
</style>
