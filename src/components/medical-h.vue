<template>
    <div class="medical-history">
        <v-sheet elevation="1" class="ma-3 pa-3">
            <div class="tab-title d-flex justify-space-between align-center">
                <h4>Medical History</h4>
                <div>
                <input v-if="search" type="text" class="seacrh-input pa-1 grey lighten-3" style="width: 20rem;">
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
                v-for="(hs, i) in history"
                :key="i">
                    <div id="accordion">
                        <div 
                        class="d-flex justify-space-between align-center" 
                        data-toggle="collapse"
                        :data-target="'#' + hs.id"
                        :aria-controls="hs.id" 
                        :id="hs.target">
                            <p>{{ hs.date }} <br> {{ hs.month }}</p>
                            <p class="ml-3">{{ hs.title }} <span class="red--text">{{ hs.dr }}</span></p>
                            <p>11.30PM</p>
                        </div>
                        <div :id="hs.id" class="collapse" :aria-labelledby="hs.target" data-parent="#accordion">
                            <div class="card-header">
                                <h5>Your symptoms</h5>
                                <p>{{ hs.symptoms }}</p>
                                <h5>Doctors Note</h5>
                                <p>{{ hs.note1 }}</p>
                                <p>{{ hs.note2 }}</p>
                                <h5>Next visit</h5>
                                <div class="d-flex">
                                    <v-chip dark style="width: 6rem;">{{ hs.nextDate }}</v-chip>
                                    <v-btn text color="red" class="btn ml-3">Re-schedule</v-btn>
                                </div>
                            </div>
                        </div>  
                    </div>
                    <v-divider></v-divider>
                </v-timeline-item>
            </v-timeline>
        </v-sheet>
    </div>
</template>

<script>
export default {
    data() {
        return {
            more: false,
            search: false,
            history: [
                {id: 'collapseOne', target: 'headingOne', date: '8', month: 'Apr', title: 'Removal Stitches', time: '11.00PM', symptoms: 'Seeing difficulty', note1: 'Required blood do', note2: 'Bile leak', nextDate: '03-04-2020'},
                {id: 'collapseTwo', target: 'headingTwo', date: '5', month: 'Apr', title: 'Cholecystectomy Surgery', dr: 'Dr. Paiki', time: '07.00PM', symptoms: 'Seeing difficulty', note2: 'Bile leak', nextDate: '03-04-2020'},
                {id: 'collapseThree', target: 'headingThree', date: '4', month: 'Apr', title: 'Gall Stones Diagnosis', time: '16.20PM', symptoms: 'Seeing difficulty', note2: 'Bile leak', nextDate: '03-04-2020'},
                {id: 'collapseFour', target: 'headingFour', date: '13', month: 'Mar', title: 'General Physical check-up', dr: 'Dr. Mwangi', time: '11.00PM', symptoms: 'Seeing difficulty', note1: 'Required blood donation', note2: 'Bile leak', nextDate: '03-04-2020'},
                {id: 'collapseFive', target: 'headingFive', date: '13', month: 'Feb', title: 'Influenza', time: '15.03PM', symptoms: 'Seeing difficulty', note1: 'Required blood donation', nextDate: '03-04-2020'},
                {id: 'collapseSix', target: 'headingSix', date: '4', month: 'Jan', title: 'Health Check up', time: '15.20PM', symptoms: 'Seeing difficulty', note1: 'Required blood donation', nextDate: '03-04-2020'}
            ]
        }
    }
}
</script>

<style scoped>

.panel-heading:hover {
    text-decoration: none;
    cursor: pointer;
}

.seacrh-input {
    border-radius: 5px;
    margin-right: 30px;
    background-color: #efefef;
}

.btn {
    text-transform: capitalize;
}

</style>