<template>
  <div>
    <!-- <div class="row no-gutters justify-content-center">
      <div class="x-container-dk">
        <div class="row no-gutters justify-content-center">
          <div class="x-container-dk">
            <div class="col-sm-12 col-md-8 mx-auto mb-5">
              <div class="seat-intro text-center">
                <h2 clas="mb-5">Get the best seat</h2>
                <hr class="col-sm-1" />
                <p class="seat-caption">
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                  Curabitur suscipit est id dictum faucibus. Etiam fringilla
                  ante at magna molestie, eget vestibulum libero ultricies.
                  Vestibulum ante ipsum primis in faucibus orci luctus et
                  ultrices posuere cubilia Curae; Cras sed dolor vitae
                </p>
              </div>
            </div>
            <div class="col-sm-12">
             <seatLayout :seats="seats" />
            </div>
          </div>
        </div>
      </div>
    </div> -->
    <bestSeatInfo :seats="seats"/>


  </div>
</template>

<script>
import $seats from "../js/seatNo";
import bestSeatInfo from "../component/bestSeatInfo.vue";


export default {
  name: "App",
  components: {
    bestSeatInfo,
  },
  data() {
    return {
      seats: $seats.seats,
    };
  },
  methods: {},
  mounted: function () {},
};
</script>