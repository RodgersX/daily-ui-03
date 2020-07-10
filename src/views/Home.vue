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

        <!-- tab data -->
        <div class="tabs">
          <div class="tab d-flex justify-space-between px-4">
            <button class="tablinks" @click="openTab(event, 'medical')" id="defaultOpen">Medical H.</button>
            <button class="tablinks" @click="openTab(event, 'personal')">Personal Info.</button>
            <button class="tablinks" @click="openTab(event, 'appointments')">Appointments</button>
          </div>

          <div id="medical" class="tabcontent">
            <medical-h />
          </div>
          <div id="personal" class="tabcontent">
            <personal-info />
          </div>
          <div id="appointments" class="tabcontent">
            <appointments />
          </div>
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
              v-for="(tile, i) in tiles"
              :key="i"
              @click="openTab(event, tile.name)">
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

  mounted() {
    document.getElementById('defaultOpen').click()
  },

  data() {
    return {
      tab: null,
      search: false,
      sheet: false,
      tiles: [
        {img: 'bx bx-list-ul bx-sm', title: 'Medical History', name: 'medical'},
        { img: 'bx bxs-user-detail bx-sm', title: 'Personal Information', name: 'personal'},
        {img: 'bx bxs-calendar bx-sm', title: 'Appointments', name: 'appointments'}
      ]
    }
  },

  methods: {
    openTab(evt, tabName) {
      // eslint-disable-next-line no-unused-vars
      var i, tabcontent, tablinks

      tabcontent = document.getElementsByClassName('tabcontent')
      for(i=0; i<tabcontent.length; i++) {
        tabcontent[i].style.display = 'none'
      }
      tablinks = document.getElementsByClassName('tablinks')
      for(i=0; i<tablinks.length; i++) {
        tablinks[i].className = tablinks[i].className.replace('active', '')
      }

      document.getElementById(tabName).style.display = 'block'
      evt.currentTarget.className += 'active'
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

.tab {
  overflow: hidden;
  border:  1px solid #ccc;
  background-color: #f1f1f1;
}

.tab button {
  background-color: inherit;
  width: 100%;
  float: left;
  border: none;
  outline: none;
  cursor: pointer;
  padding: 14px 16px;
  transition: 0.3s;
}

.tab button:hover {
  background-color: #ddd;
}

.tab button.active {
  background-color: #ccc;
  border-bottom: 1px solid red;
}

.tabcontent {
  display: none;
  border-top: none;
}
</style>