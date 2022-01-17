<template>
  <div class="rocket-card">
    <p>{{ nom }}</p>
    <p>{{ description }}</p>
    <img v-bind:src="image" alt="oups le logo ne s'affiche pas">
    <p>{{ success_rate }}%</p>
    <p>{{ hauteur }}m</p>
    <p>{{ diametre }}m</p>
    <p>{{ masse }} Kg</p>
    <p>{{ moteur_nb }} moteur de type {{ moteur_type }}</p>
  </div>
</template>

<script>
const axios = require('axios').default;
export default {
  name: 'rocket-item',
  data() {
    return {
      nom: null,
      description: null,
      success_rate: null,
      image: null,
      hauteur: null,
      diametre: null,
      masse: null,
      moteur_nb: null,
      moteur_type: null,
    }
  },
  mounted() {
    axios.get('https://api.spacexdata.com/v4/rockets/5e9d0d95eda69974db09d1ed')
    .then(response => {
      this.nom = response.data.name;
      this.description = response.data.description;
      this.success_rate = response.data.success_rate_pct;
      this.image = response.data.flickr_images[0];
      this.hauteur = response.data.height.meters;
      this.diametre = response.data.diameter.meters;
      this.masse = response.data.mass.kg;
      this.moteur_nb = response.data.engines.number;
      this.moteur_type = response.data.engines.type
    });
  }
}
</script>