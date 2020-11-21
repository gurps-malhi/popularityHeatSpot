<template>
    <div>
        <div class="seating">
        <div class="stage">
        <h5>Stage</h5>
        </div>
        <div class="seating-container">
            <div class="outer-circle" v-for="(seat, index) in seats" :key="index">
                {{seat.seatNo}}   
            <transition name="fade">
            <div class="pop-circle" :id="seat.seatNo"  v-if="!check_pop" :style="{ width:seat.popularity + 'px', height:seat.popularity + 'px' }">  
            </div>
            </transition>
            </div>
        </div>
        </div>
        <div class="text-center mb-5">
            <button v-on:click="toggle()" class="btn btn-dark d-inline-block px-3 py-2 rounded">
            <span v-show="check_pop">Show</span>
            <span v-show="!check_pop">Hide</span>  
            seat popularity 
            </button>
        </div>
    </div>
</template>

<script>

export default {
 props:['seats'],
 data() {
     return {
      check_pop: true,
      runOnce: true,
      timesBy: 3
     };
 },
 methods:{
      toggle:function(){
    if(this.check_pop){
      let popString = '';
      if(this.runOnce){
      for(let i = 0; i<=this.seats.length -1; i++){
          popString = this.seats[i].popularity;
          if(popString.includes("%")){
            popString.slice(0, -1);
            popString = parseInt(popString);
          }
          this.seats[i].popularity = popString * this.timesBy;
          popString = '';
      }
      this.runOnce = false;
    }
      this.check_pop = false;
    }else{
      this.check_pop = true;
    }
  },
 },
}
</script>

<style>

</style>