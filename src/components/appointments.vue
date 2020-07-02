<template>
    <div class="appointments">
        <v-sheet elevation="1" class="ma-3 pa-3">
            <div class="tab-title d-flex justify-space-between align-center">
                <h4>Appointments</h4>
                <div>
                    <v-btn rounded depressed color="#f9a8a6">
                        <i class="bx bx-plus bx-sm"></i>
                        create
                    </v-btn>
                </div>
            </div>
            <v-timeline dense>
                <v-timeline-item
                fill-dot
                small
                color="red"
                v-for="(app, i) in appointments"
                :key="i">
                    <v-list>
                        <v-list-item>
                            <v-list-item-content class="text-center">
                                <p>{{ app.date }}</p>
                                <p>{{ app.month }}</p>
                            </v-list-item-content>
                            <v-list-item-content class="text-center">
                                <p>{{ app.title }}</p>
                            </v-list-item-content>
                            <v-list-item-content class="text-center">
                                <P>{{ app.time }}</P>
                            </v-list-item-content>
                        </v-list-item>
                        <v-divider></v-divider>
                    </v-list>
                </v-timeline-item>
            </v-timeline>
        </v-sheet>
    </div>
</template>

<script>
export default {
    data() {
        return {
             appointments: [
                {date: '8', month: 'Apr', title: 'Removal Stitches', time: '11.00PM'},
                {date: '4', month: 'Apr', title: 'Gall Stones Diagnosis', time: '16.20PM'},
                {date: '13', month: 'Feb', title: 'Influenza', time: '15.03PM'},
            ]
        }
    }
}
</script>