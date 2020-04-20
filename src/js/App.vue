<template>
    <div>
    
    <div class="seating">
      <div class="stage">
      <h5>Stage</h5>
    </div>
      <div class="seating-container">
        <div class="outer-circle" v-for="seat in seats">
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
  name: 'App',
  data() {
    return {
      message: '',
      seats:$seats,
      check_pop: true,
      runOnce: true,
      timesBy: 2
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
  }
  },
  mounted:function(){
  
}
};

 var $seats = [
     {
      "seatNo": 1,
      "popularity":"10%",
    },
     {
      "seatNo": 2,
      "popularity":"17%",
    },
    {
      "seatNo": 3,
      "popularity":"0%",
    },
     {
      "seatNo": 4,
      "popularity":"50%",
    },
     {
      "seatNo": 5,
      "popularity":"17%",
    },
    {
      "seatNo": 6,
      "popularity":"0%",
    },
    {
      "seatNo": 7,
      "popularity":"0%",
    },
     {
      "seatNo": 8,
      "popularity":"50%",
    },
     {
      "seatNo": 9,
      "popularity":"17%",
    },
    {
      "seatNo": 10,
      "popularity":"70%",
    },
    {
      "seatNo": 11,
      "popularity":"80%",
    },
     {
      "seatNo": 12,
      "popularity":"90%",
    },
    {
      "seatNo": 13,
      "popularity":"23%",
    },
     {
      "seatNo": 14,
      "popularity":"40%",
    },
     {
      "seatNo": 15,
      "popularity":"17%",
    },
    {
      "seatNo": 16,
      "popularity":"0%",
    },
    {
      "seatNo": 17,
      "popularity":"0%",
    },
     {
      "seatNo": 18,
      "popularity":"50%",
    },
     {
      "seatNo": 19,
      "popularity":"17%",
    },
    {
      "seatNo": 20,
      "popularity":"0%",
    },
    {
      "seatNo": 21,
      "popularity":"40%",
    },
    {
      "seatNo": 22,
      "popularity":"30%",
    },
    {
      "seatNo": 23,
      "popularity":"80%",
    },
     {
      "seatNo": 23,
      "popularity":"80%",
    },
    
 ]
</script>