<template>
  <div class="home">
    <div class="card-main">
      <div class="card-item">
        <div class="image-div d-flex justify-center align-center red">
          <div class="text-center white--text">
            <v-avatar size="100" color="white">
              <img src="@/assets/profile.jpg">
            </v-avatar>
            <h3>MAWIRA BRIAN</h3>
            <P>Last logged in 2 days ago</P>
          </div>
        </div>

        <!-- tabular data -->
        <div class="tabs">
          <v-tabs text fixed-tabs color="black">
            <v-tab class="tab-title" href="#tab-1">Medical H.</v-tab>
            <v-tab class="tab-title" href="#tab-2">Personal Info.</v-tab>
            <v-tab class="tab-title" href="#tab-3">Appointments</v-tab>

            <!-- tabs items -->
            <v-tab-item id="tab-1">
              <medical-h />
            </v-tab-item>
            <v-tab-item id="tab-2">
              <personal-info />
            </v-tab-item>
            <v-tab-item id="tab-3">
              <appointments />
            </v-tab-item>
          </v-tabs>
            
        </div>
      </div>
    </div>

    <div class="bottom-nav">
      <bottom-nav />
    </div>

  </div>
</template>

<script>
import history from '@/components/medical-h'
import personalInfo from '@/components/personal-info'
import appointments from '@/components/appointments'
import bottomNav from '@/components/bottom-nav'

export default {
  components: {
    'bottom-nav': bottomNav,
    'medical-h': history,
    'personal-info': personalInfo,
    appointments
  },

  data() {
    return {
      tab: null,
      search: false
    }
  }
}
</script>

<style scoped>

.image-div {
  height: 300px;
}

.tab-title:hover {
  text-decoration: none;
}

.bottom-nav {
  position: fixed;
  bottom: 0;
  background: white;
  width: 100%;
  border-top: 1px solid #dddcdc;
  height: 60px;
}
</style>