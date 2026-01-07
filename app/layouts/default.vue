<template>
    <div>
        <v-app>
        <!--Navigation -->
        <v-navigation-drawer
        v-model="drawer"



      >
        <v-list>
          <v-list-item
           to="/dashboard"
            prepend-avatar="https://i.pinimg.com/736x/4b/e6/7f/4be67f67f0fca883770e96112711ecbe.jpg"
            subtitle="franznavarro260@gmail.com"
            title="Franz Navarro"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item to="/" prepend-icon="mdi mdi-view-dashboard" title="Dashboar" value="dashboard"></v-list-item>
          <v-list-item to="/inventory" prepend-icon="mdi mdi-list-box" title="Inventory" value="shared"></v-list-item>
          <v-list-item to="/category"prepend-icon="mdi mdi-account-group-outline" title="Category" value="category"></v-list-item>
          <v-list-item to="/users"prepend-icon="mdi mdi-account-group-outline" title="Users" value="user"></v-list-item>
        </v-list>
      </v-navigation-drawer>


        <!--Appbar -->
        <v-app-bar :elevation="2">
  <template v-slot:prepend>
    <v-app-bar-nav-icon @click.stop="drawer =! drawer"></v-app-bar-nav-icon>
  </template>

  <v-app-bar-title>Application Bar</v-app-bar-title>
</v-app-bar>



            <v-main>
                <v-container fluid>
                <slot />
                </v-container>
            </v-main>
        </v-app>
    </div>

</template>

    <script  setup>
    const drawer = ref(true)

    </script>