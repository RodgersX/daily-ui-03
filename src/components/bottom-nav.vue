<template>
    <div class="bottom-nav d-flex justify-center align-center">
        <ul style="list-style: none;">
            <li class="bottom-nav__item">
                <v-btn icon color="red">
                    <i class="bx bx-home bx-sm"></i>
                </v-btn>
            </li>
            <li class="bottom-nav__item">
                <v-btn icon color="red">
                    <i class="bx bx-calendar-alt bx-sm"></i>
                </v-btn>
            </li>
            <li class="bottom-nav__item">
                <v-btn icon color="red">
                    <i class="bx bx-user bx-sm"></i>
                </v-btn>
            </li>
            <li class="bottom-nav__item">
                <v-btn icon color="red">
                    <i class="bx bx-cog bx-sm"></i>
                </v-btn>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>

.bottom-nav__item {
    display: inline-block;
    margin: 0 1.5rem;
}
</style>