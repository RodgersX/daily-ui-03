<template>
    <div class="test">
        <div class="panel-group" id="accordion">
            <div class="panel panel-default">
                <div class="panel-heading">
                        <a data-toggle="collapse" data-parent="#accordion" href="#collapse1">
                            <v-list>
                                <v-list-item>
                                <v-list-item-content class="text-center">
                                    <p>8</p>
                                    <p>Apr</p>
                                </v-list-item-content>
                                <v-list-item-content class="text-center">
                                    <p>Endoscopy</p>
                                    <p class="red--text">Dr. Kiarie</p>
                                </v-list-item-content>
                                <v-list-item-content class="text-center">
                                    <P>11.30PM</P>
                                </v-list-item-content>
                                </v-list-item>
                                <v-divider></v-divider>
                            </v-list>
                        </a>
                </div>
                <div id="collapse1" class="panel-collapse collapse in">
                    <div class="panel-body">Lorem ipsum dolor sit amet, consectetur adipisicing elit,
                    sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
                    minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
                    commodo consequat.</div>
                </div>
            </div>           
        </div>
    </div>
</template>

<style scoped>
.panel-heading a:hover {
    text-decoration: none;
}
</style>