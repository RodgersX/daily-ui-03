<template>
  <div class="test">
    <!-- tab links -->
    <div class="tab">
      <button class="tablinks" @click="openCity(event, 'London')" id="defaultOpen">London</button>
      <button class="tablinks" @click="openCity(event, 'Paris')">Paris</button>
      <button class="tablinks" @click="openCity(event, 'Tokyo')">Tokyo</button>
    </div>

    <!-- tab content -->
    <div id="London" class="tabcontent">
      <h3>London</h3>
      <p>London is the capital city of England</p>
    </div>
    <div id="Paris" class="tabcontent">
      <h3>Paris</h3>
      <p>Paris is the capital city of France</p>
    </div>
    <div id="Tokyo" class="tabcontent">
      <h3>Tokyo</h3>
      <p>Tokyo is the capital city of Japan</p>
    </div>
  </div>
</template>

<script>
  export default {
    mounted() {
      document.getElementById('defaultOpen').click()
    },

    data() {
      return {

      }
    },

    methods: {
      openCity(evt, cityName) {
        var i, tabcontent, tablinks

        tabcontent = document.getElementsByClassName('tabcontent')
        for(i=0; i<tabcontent.length; i++) {
          tabcontent[i].style.display = 'none'
        }

        tablinks = document.getElementsByClassName('tablinks')
        for(i=0; i<tablinks[i].length; i++) {
          tablinks[i].className = tablinks[i].className.replace('active', '')
        }

        document.getElementById(cityName).style.display = 'block'
        evt.currentTarget.className += 'active'
      }
    }
  }
</script>

<style scoped>

.tab {
  overflow: hidden;
  border:  1px solid #ccc;
  background-color: #f1f1f1;
}

.tab button {
  background-color: inherit;
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
}

@keyframes fadeEffect {
  from {opacity: 0;}
  to {opacity: 1;}
}

.tabcontent {
  display: none;
  padding: 6px 12px;
  border: 1px solid #ccc;
  border-top: none;
  animation: fadeEffect 2s;
}
</style>