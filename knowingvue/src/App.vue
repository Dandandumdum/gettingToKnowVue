<template>
  <div id="app">
    <h3>Bands</h3>

    <ul>
      <li v-for="band of bands" :key="band" :class="{ 'favouriteBand': band === favouriteBand}">{{band}} <button @click="addBand(band)">Add</button></li>
    </ul>
      
      <div v-if="favouriteBands.length > 0">
      <h3>Favourite Bands</h3>

    <ul>
      <li v-for="band of favouriteBands" :key="band">{{band}} <button @click="removeBand(band)">Remove</button></li>
    </ul>

    <input type="text" name="favouriteBand" id="favouriteBand" v-model="favouriteBand">
      </div>
      <div v-else>
        <h3>No favourites yet...</h3>

      </div>
    
    
  </div>
  
</template>

<script>

export default {
  name: 'App',
  data() {
    return{
      bands: [
        "Megmeth",
        "NXSX",
        "John's band"
      ],
      favouriteBands:[
      ],
      favouriteBand: ''
    }
  },
  methods: {
    addBand(band){
      if(!this.favouriteBands.includes(band)){
          this.favouriteBands.push(band)
      }
      
    },
    removeBand(band){
        this.favouriteBands.pop(band)
       
    }
  }
  
}
</script>

<style>
  .favouriteBand {
    color: blueviolet;
  }
</style>
