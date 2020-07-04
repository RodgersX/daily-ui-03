<template>
  <div class="home">
    <div class="card-main">
      <div class="card-item">
        <div class="px-2 pt-2 top-nav red d-flex justify-space-between">
          <v-btn icon dark><i class="bx bx-arrow-back bx-sm"></i></v-btn>
          <v-btn icon dark><i class="bx bx-x bx-sm"></i></v-btn>
        </div>
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

    <div class="bottom-nav d-flex justify-center align-center">
        <div class="text-center">
          <v-bottom-sheet v-model="sheet">
            <template class=" d-flex justify-center align-center" v-slot:activator="{ on, menu }">
              <ul style="list-style: none;">
                  <li class="bottom-nav__item">
                      <v-btn
                      icon
                      color="red">
                          <i class="bx bx-home bx-sm"></i>
                      </v-btn>
                  </li>
                  <li class="bottom-nav__item">
                      <v-btn icon color="red">
                          <i class="bx bx-calendar-alt bx-sm"></i>
                      </v-btn>
                  </li>
                  <li class="bottom-nav__item">
                      <v-btn 
                      icon 
                      color="red" 
                      v-on="on"
                      v-bind="menu">
                          <i class="bx bx-user bx-sm"></i>
                      </v-btn>
                  </li>
                  <li class="bottom-nav__item">
                      <v-btn icon color="red">
                          <i class="bx bx-cog bx-sm"></i>
                      </v-btn>
                  </li>
              </ul>
            </template>
            <v-list>
              <v-list-item
              class="v-list-item"
              v-for="tile in tiles"
              :key="tile.title"
              :href="'#tab-' + 3">
                <v-list-item-avatar>
                  <v-avatar size="32px" tile>
                    <i :class='tile.img' class="grey--text"></i>
                  </v-avatar>
                </v-list-item-avatar>
                <v-list-item-title>{{ tile.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-bottom-sheet>
        </div>
    </div>

  </div>
</template>

<script>
import history from '@/components/medical-h'
import personalInfo from '@/components/personal-info'
import appointments from '@/components/appointments'

export default {
  components: {
    'medical-h': history,
    'personal-info': personalInfo,
    appointments
  },

  data() {
    return {
      tab: null,
      search: false,
      sheet: false,
      tiles: [
        {img: 'bx bx-list-ul bx-sm', title: 'Medical History'},
        { img: 'bx bxs-user-detail bx-sm', title: 'Personal Information'},
        {img: 'bx bxs-calendar bx-sm', title: 'Appointments'}
      ]
    }
  }
}
</script>

<style scoped>

.image-div {
  height: 250px;
}

.tab-title:hover,
.v-list-item {
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

.bottom-nav__item {
    display: inline-block;
    margin: 0 1.5rem;
}
</style>