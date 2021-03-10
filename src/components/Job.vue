<template>
  <div class="col-4">
    <router-link :to="{name: 'JobDetails', params: {id: job._id}}" >
      <div class="jobd job">
        <div class="jobd-body">
          <h4 class="jobd-title">{{job.company}} | {{job.jobTitle}}</h4>
          <p class="jobd-text">{{job.rate}} | {{job.description}}</p>
        </div>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'job',
  props: {
    job: Object
  },
  setup() {
    return {}
  },
  components: {}
}
</script>

<style scoped>
.job:hover {
  transform: translateY(-5px);
  box-shadow: 1px 3px 5px rgb(94, 94, 94);
  cursor: pointer
}

.job {
  transition: all .2s;
  color: black
}
</style>
