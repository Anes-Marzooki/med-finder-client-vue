<template lang="pug">
  div
    v-app-bar(color="primary" dense='')
      v-app-bar-nav-icon
      v-toolbar-title My Pharmacy
      v-spacer
      
      v-btn(icon='')
        v-icon mdi-heart
      v-btn(icon='')
        v-icon mdi-magnify
      v-btn(text v-if="$auth.isAuthenticated" @click="logout")
        |Logout
        v-icon(right) fa fa-sign-in
      v-menu(left='' bottom='')
        template(v-slot:activator='{ on }')
          v-btn(icon='' v-on='on')
            v-icon mdi-dots-vertical
        v-list
          v-list-item(v-for='n in 5' :key='n' @click='() => {}')
            v-list-item-title Option {{ n }}
    medTable
</template>





<script>
import medTable from "./table.vue";
export default {
  methods: {
    // Log the user out
    logout() {
      this.$auth.logout({
        returnTo: window.location.origin
      });
    }
  },
  components: {
    medTable: medTable
  }
};
</script>