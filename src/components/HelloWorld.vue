

<template>
  <div>
 <article v-for="(location, idx) in locations" :key="idx">
  <img class="picture" :src="location.images">
  <h1>{{ location.name }}</h1>
 </article>
</div>
</template>

<script>
import { db } from '../main'
import './HelloWorld.css'

export default {
 name: 'HelloWorld',
 data () {
   return {
     locations: []
   }
 },
 firestore () {
   return {
     locations: db.collection('locations').orderBy('createdAt')
   }
 }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

.picture {
    width: 500px;
    border-radius: 10px;
}
</style>
