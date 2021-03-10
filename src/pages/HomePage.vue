<template>
  <div class="home container">
    <div class="row mt-5">
      <div class="col">
        <h1 id="welcome" class='text-center text-warning'>Select a Category</h1>
      </div>
    </div>
    <div class="row mt-5 d-flex justify-content-center">
      <div class="col">
      <button id='button' type="button" class="btn btn-outline-dark"><img src="https://img.pngio.com/car-icon-white-407480-free-icons-library-car-png-circle-512_512.jpg" class="img-fluid ${3|rounded-top,rounded-right,rounded-bottom,rounded-left,rounded-circle,|}" alt=""></button>
      </div>
      <div class="col">
      <button id='button' type="button" class="btn btn-outline-dark"><img src="http://iconsetc.com/icons-watermarks/flat-circle-white-on-black/broccolidry/broccolidry_house/broccolidry_house_flat-circle-white-on-black_512x512.png" class="img-fluid ${3|rounded-top,rounded-right,rounded-bottom,rounded-left,rounded-circle,|}" alt=""></button>
      </div>
      <div class="col">
      <button id='button' type="button" class="btn btn-outline-dark"><img src="https://banner.uclipart.com/20200112/fbh/job-black-and-white-symbol.png" class="img-fluid ${3|rounded-top,rounded-right,rounded-bottom,rounded-left,rounded-circle,|}" alt=""></button>
      </div>
    </div>
  </div>
</template>

<script>
import { reactive } from 'vue'

export default {
  name: 'Home',
  setup() {
    const state = reactive({})
    return {
      methodName() {

      }
    }
  },
  components: {
  }
}
</script>
