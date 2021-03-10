<template>
  <div class="col-4">
    <router-link :to="{name: 'HouseDetails', params: {id: house._id}}" >
      <div class="housed house">
        <img class="housed-img-top" :src="house.imgUrl" alt="house">
        <div class="housed-body">
          <h4 class="housed-title">{{house.bedrooms}} | {{house.bathrooms}}</h4>
          <p class="housed-text">{{house.year}} | {{house.price}}</p>
        </div>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'house',
  props: {
    house: Object
  },
  setup() {
    return {}
  },
  components: {}
}
</script>

<style scoped>
.house:hover {
  transform: translateY(-5px);
  box-shadow: 1px 3px 5px rgb(94, 94, 94);
  cursor: pointer
}

.house {
  transition: all .2s;
  color: black
}
</style>
