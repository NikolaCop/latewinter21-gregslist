<template>
  <div class="job-details">
    <h1>Welcome to the details page</h1>
    {{ state.job }}
    <button type="button" class="btn btn-outline-danger" @click="deleteJob">
      Delete Job
    </button>

    <form class="form-inline" onsubmit="app.jobsController.createJob(event)">
      <div class="form-group">
        <input
            type="text"
            name="company"
            id="company"
            class="form-control"
            placeholder="Company"
            aria-describedby="helpId"
          v-model="state.job.company"
        />
      </div>
      <div class="form-group">
        <input
            type="text"
            name="jobTitle"
            id="jobTitle"
            class="form-control"
            placeholder="Job Title"
            aria-describedby="helpId"
          v-model="state.job.jobTitle"
        />
      </div>
      <div class="form-group">
        <input
            type="number"
            name="rate"
            id="rate"
            class="form-control"
            placeholder="Job Title"
            aria-describedby="helpId"
          v-model="state.job.rate"
        />
      </div>
      <div class="form-group">
        <input
            type="text"
            name="description"
            id="description"
            class="form-control"
            placeholder="Description"
            aria-describedby="helpId"
          v-model="state.job.description"
        />
      </div>

      <button class="btn btn-info" type="submit">Create</button>
    </form>
  </div>
</template>

<script>
import { onMounted, reactive, computed } from 'vue'
import { onBeforeRouteLeave, useRoute, useRouter } from 'vue-router'
import { jobsService } from '../services/JobsService'
import { AppState } from '../Appstate'

export default {
  name: 'JobDetails',
  setup() {
    const route = useRoute()
    const router = useRouter()
    const state = reactive({
      job: computed(() => AppState.activeJob)
    })

    onMounted(() => {
      jobsService.getJob(route.params.id)
    })

    onBeforeRouteLeave((to, from, next) => {
      if (window.confirm('You sure bro?')) {
        AppState.activeJob = {}
        next()
      }
    })

    return {
      route,
      state,
      async deleteJob() {
        await jobsService.deleteJob(state.job._id)
        router.push({ name: 'Jobs' })
      }
    }
  },
  components: {}
}
</script>

<style lang="scss" scoped>
</style>
