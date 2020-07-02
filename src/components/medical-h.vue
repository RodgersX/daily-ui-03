<template>
    <div class="medical-history">
        <v-sheet elevation="1" class="ma-3 pa-3">
            <div class="tab-title d-flex justify-space-between align-center">
                <h4>Medical History</h4>
                <div>
                <input v-if="search" type="text" class="pa-1 grey lighten-3" style="width: 20rem;">
                <v-btn icon @click="search = true">
                    <i class="bx bx-search bx-sm"></i>
                </v-btn>
                </div>
            </div>
            <v-timeline dense>
                <v-timeline-item 
                fill-dot 
                small 
                color="red"
                v-for="hs in history"
                :key="hs.id">
                    <div class="panel-group" id="accordion">
                        <div class="panel panel-default">
                            <div class="panel-heading">
                                <a data-toggle="collapse" data-parent="#accordion" href="#collapse1">
                                    <v-list>
                                        <v-list-item>
                                        <v-list-item-content class="text-center">
                                            <p>{{ hs.date }}</p>
                                            <p>{{ hs.month }}</p>
                                        </v-list-item-content>
                                        <v-list-item-content class="text-center">
                                            <p>{{ hs.title }}</p>
                                            <p class="red--text">{{ hs.dr }}</p>
                                        </v-list-item-content>
                                        <v-list-item-content class="text-center">
                                            <p>{{ hs.time }}</p>
                                        </v-list-item-content>
                                        </v-list-item>
                                        <v-divider></v-divider>
                                    </v-list>
                                </a>
                            </div>
                            <div id="collapse1" class="panel-collapse collapse in">
                                <div class="panel-body">{{ hs.details }}</div>
                            </div>
                        </div>           
                    </div>
                </v-timeline-item>
            </v-timeline>
        </v-sheet>
    </div>
</template>

<script>
export default {
    data() {
        return {
            history: [
                {date: '8', month: 'Apr', title: 'Removal Stitches', time: '11.00PM', details: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse voluptatum est odit minus! Qui sunt repudiandae iure praesentium impedit tempora!'},
                {date: '5', month: 'Apr', title: 'Cholecystectomy Surgery', dr: 'Dr. Paiki', time: '07.00PM', details: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse voluptatum est odit minus! Qui sunt repudiandae iure praesentium impedit tempora!'},
                {date: '4', month: 'Apr', title: 'Gall Stones Diagnosis', time: '16.20PM', details: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse voluptatum est odit minus! Qui sunt repudiandae iure praesentium impedit tempora!'},
                {date: '13', month: 'Mar', title: 'General Physical check-up', dr: 'Dr. Mwangi', time: '11.00PM', details: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse voluptatum est odit minus! Qui sunt repudiandae iure praesentium impedit tempora!'},
                {date: '13', month: 'Feb', title: 'Influenza', time: '15.03PM', details: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse voluptatum est odit minus! Qui sunt repudiandae iure praesentium impedit tempora!'},
                {date: '4', month: 'Jan', title: 'Health Check up', time: '15.20PM', details: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse voluptatum est odit minus! Qui sunt repudiandae iure praesentium impedit tempora!'}
            ]
        }
    }
}
</script>

<style scoped>

.panel-heading a:hover {
    text-decoration: none;
}

</style>