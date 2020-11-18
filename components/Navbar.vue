<template>
   <div>
    
     <v-navigation-drawer v-model="rightDrawer" :left="left"  temporary  fixed >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      color="white"
    >
      <v-app-bar-nav-icon @click.stop="rightDrawer = !rightDrawer" />
    
     
      
      <v-toolbar-title v-text="title" />
      <v-toolbar-items>
       
        <v-btn :to="{ name: 'index'}" color="black" text>Home</v-btn>
        <v-btn :to="{ name: 'dashboard'}" color="black" text>Dashboard</v-btn>
       </v-toolbar-items>
      <v-spacer />
      
   <v-spacer></v-spacer>

       <v-toolbar-items v-if="!loggedIn" >
        <v-btn :to="{ name: 'auth-login'}" color="black" text>Login</v-btn>
        <v-btn :to="{ name: 'auth-register'}" color="black" text>Register</v-btn>
       </v-toolbar-items>
       <v-toolbar-items  v-if="loggedIn">
        <v-btn @click.prevent="signOut" color="black" text>logout</v-btn>
       </v-toolbar-items>

    </v-app-bar>


  </div>
</template>


<script>

export default {
  methods: {
        signOut() {
            this.$auth.logout();
        }
    },
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      left: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
}
</script>

<style>

</style>