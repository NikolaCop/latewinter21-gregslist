<template>
<div class="jobs-page container">
    <div class="row">
      <div class="col text-center">
        <h1>Jobs</h1>
      </div>
    </div>
    <div class="row my-3">
      <form class="form-inline" @submit.prevent="createJob">
        <div class="form-group">
          <input
            type="text"
            name="company"
            id="company"
            class="form-control"
            placeholder="Company"
            aria-describedby="helpId"
            v-model="state.newJob.company"
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
            v-model="state.newJob.jobTitle"
          />
        </div>
        <div class="form-group">
          <input
            type="number"
            name="rate"
            id="rate"
            class="form-control"
            placeholder="Rate"
            aria-describedby="helpId"
            v-model="state.newJob.rate"
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
            v-model="state.newJob.description"
          />
        </div>
        <button class="btn btn-info" type="submit">Create</button>
      </form>
    </div>
    <div class="row">
      <Job v-for="jobData in state.jobs" :key="jobData._id" :job="jobData" />
    </div>
  </div>
</template>

<script>
import { reactive, computed, onMounted } from 'vue'
import { AppState } from '../Appstate'
import { jobsService } from '../services/JobsService'
import Job from '../components/Job'
import { useRouter } from 'vue-router'

export default {
  name: 'JobsPage',
  setup() {
    const router = useRouter()
    const state = reactive({
      jobs: computed(() => AppState.jobs),
      newJob: {}
    })
    onMounted(() => {
      jobsService.getJobs()
    })
    return {
      state,
      async createJob() {
        const jobId = await jobsService.createJob(state.newJob)
        router.push({ name: 'JobDetails', params: { id: jobId } })
        state.newJob = {}
      }
    }
  },
  components: {
    Job
  }
}
</script>

<style lang="scss" scoped>
</style>
