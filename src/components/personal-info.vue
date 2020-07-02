<template>
    <div class="personal-info">
        <v-sheet elevation="1" class="ma-2 mb-12 pa-2">
            <v-tabs text centered hide-slider color="black">
                <v-tab class="tab-title" href="#profile">Profile</v-tab>
                <v-tab class="tab-title" href="#address">Address</v-tab>
                <v-tab class="tab-title" href="#membership">Membership</v-tab>

                <v-tab-item id="profile">
                    <form action="#" method="post" class="mt-4">
                        <div class="form-group">
                            <label for="email">Age:</label>
                            <input type="email" name="email" class="form-control" placeholder="y/o">
                        </div>
                        <div class="form-group">
                            <label for="firstname">Firstname:</label>
                            <input type="text" name="firstname" class="form-control" placeholder="firstname">
                        </div>
                        <div class="form-group">
                            <label for="lastname">Firstname:</label>
                            <input type="text" name="lastname" class="form-control" placeholder="lastname">
                        </div>
                    </form>
                </v-tab-item>
                <v-tab-item id="address">
                    <form action="#" method="post" class="mt-4">
                        <div class="form-group">
                            <label for="phone">Phone:</label>
                            <input type="phone" name="phone" class="form-control" placeholder="0723456789">
                        </div>
                        <div class="form-group">
                            <label for="email">Email:</label>
                            <input type="email" name="email" class="form-control" placeholder="you@example.com">
                        </div>
                        <div class="form-group">
                            <label for="location">Location:</label>
                            <input type="text" name="location" class="form-control" placeholder="Juja, Kiambu">
                        </div>
                    </form>
                </v-tab-item>
                <v-tab-item id="membership">
                    <form action="#" method="post" class="mt-4">
                        <div class="form-group">
                            <label for="id">Membership ID:</label>
                            <input type="text" name="id" class="form-control" placeholder="KE-0000">
                        </div>
                        <div class="form-group">
                            <label for="premium">Membership:</label>
                            <input type="text" name="premium" class="form-control" placeholder="GOLD">
                        </div>
                        <div class="form-group">
                            <label for="amount">Amount Due:</label>
                            <input type="text" name="amount" class="form-control" placeholder="Kshs. 212,345">
                        </div>
                        <div class="form-group">
                            <label for="dueDate">Next Payment:</label>
                            <input type="date" name="dueDate" class="form-control" placeholder="16/03/2021">
                        </div>
                        <button type="submit" class="btn">PAY NOW</button>
                    </form>
                </v-tab-item>
            </v-tabs>
        </v-sheet>
    </div>
</template>


<style scoped>
.nav li {
    margin: 0 2rem;
}

.nav li a {
    color: black;
}

.tab-title:hover {
    text-decoration: none;
}

.form-control {
    outline: none;
    background: #efefef;
}

.btn {
    color: #094209;
}

</style>