<template>
  <v-app>
    <v-sheet
      width="100%"
      height="50"
    >
      <!-- บาร์ด้านบน -->
      <v-toolbar color="white" flat>
        <v-btn icon href="./Home">
          <v-icon color="grey lighten-1" small>
            mdi-arrow-left-thick
          </v-icon>
        </v-btn>
        <v-toolber-title class="black--text">
          แจ้งเตือน
        </v-toolber-title>
        <v-spacer />
        <v-btn icon>
          <v-icon color="grey lighten-1" normal>
            mdi-dots-vertical
          </v-icon>
        </v-btn>
      </v-toolbar>
    </v-sheet>
    <v-card light>
      <v-list
        subheader
        three-line
        light
      >
        <v-subheader>User Controls</v-subheader>

        <v-list
          subheader
          three-line
          light
        >
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>Password</v-list-item-title>
              <v-list-item-subtitle>Require password for purchase or use password to restrict purchase</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider />

        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Password</v-list-item-title>
            <v-list-item-subtitle>Require password for purchase or use password to restrict purchase</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider />
      <v-list
        subheader
        three-line
        light
      >
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Password</v-list-item-title>
            <v-list-item-subtitle>Require password for purchase or use password to restrict purchase</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider />
      <v-list
        subheader
        three-line
        light
      >
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Password</v-list-item-title>
            <v-list-item-subtitle>Require password for purchase or use password to restrict purchase</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider />
      <v-list
        subheader
        three-line
        light
      >
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Password</v-list-item-title>
            <v-list-item-subtitle>Require password for purchase or use password to restrict purchase</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-divider />
    </v-card>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    items: [
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
        title: 'Brunch this weekend?',
        subtitle: '<span class="text--primary black--text">Ali Connors</span> &mdash; I\'ll be in your neighborhood doing errands this weekend. Do you want to hang out?'
      },
      { divider: true, inset: true },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
        title: 'Summer BBQ <span class="grey--text text--lighten-1">4</span>',
        subtitle: '<span class="text--primary black--text">to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I\'m out of town this weekend.'
      },
      { divider: true, inset: true },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
        title: 'Oui oui',
        subtitle: '<span class="text--primary black--text">Sandra Adams</span> &mdash; Do you have Paris recommendations? Have you ever been?'
      },
      { divider: true, inset: true },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
        title: 'Birthday gift',
        subtitle: '<span class="text--primary black--text">Trevor Hansen</span> &mdash; Have any ideas about what we should get Heidi for her birthday?'
      },
      { divider: true, inset: true },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
        title: 'Recipe to try',
        subtitle: '<span class="text--primary black--text">Britta Holt</span> &mdash; We should eat this: Grate, Squash, Corn, and tomatillo Tacos.'
      }
    ]
  })
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&family=Sarabun:wght@200&display=swap');

 .fa{
   font-family: 'Open Sans';
   font-family: 'Sarabun', sans-serif;
 }
 .theme--dark.v-application .text--primary {
    color: #000 !important;
}
</style>
