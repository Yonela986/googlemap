<template>
  <div>
    <h2> Google Maps </h2>
 
    <gmap-map
      :center="center"
      :zoom="10"
      style="width:100%;  height: 555px;">
      <gmap-marker
        :key="index"
        v-for="(gmp, index) in locations"
        :position="gmp"
        @click="center=gmp"
        icon="./assets/icon.png"
      ></gmap-marker>
    </gmap-map>
 
  </div>
</template>
 
<script>
export default {
  name: "GoogleMap",
  data() {
    return {
      center: { 
         lat: -33.876115,
         lng: 18.5008116,
      },
      locations: [],
      currentLocation: null
    };
  },
 
  mounted() {
    this.setLocationLatLng();
  },
 
  methods: {
    setPlace(loc) {
      this.currentLocation = loc;
    },
    setLocationLatLng: function() {
        navigator.geolocation.getCurrentPosition(geolocation => {
          this.center = {
            lat: geolocation.coords.latitude,
            lng: geolocation.coords.longitude
          };
        });
 
        this.locations = [
          
          {
              lat: -33.9685533,
              lng: 18.5662383,
              label: '310'
          },
          {
              lat: -34.0461583,
              lng: 18.7047383,
              label: '0'
          },
          {
              lat: -31.8942983,
              lng: 26.878175,
              label: '299'
          }
      ];
 
    }
  }
};
</script>