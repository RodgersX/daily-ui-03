<template>
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
          v-for="tile in tiles"
          :key="tile.title"
          @click="sheet = false"
        >
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
</template>

<script>
  export default {
    data: () => ({
      sheet: false,
      tiles: [
        {img: 'bx bx-list-ul bx-sm', title: 'Medical History'},
        { img: 'bx bxs-user-detail bx-sm', title: 'Personal Information'},
        {img: 'bx bxs-calendar bx-sm', title: 'Appointments'}
      ]
    }),
  }
</script>

<style scoped>
.bottom-nav__item {
    display: inline-block;
    margin: 0 1.5rem;
}
</style>