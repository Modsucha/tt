<template>
  <v-app class="ma-2 fa">
    <v-sheet height="50" light>
      <v-toolbar color="rgba(0,0,0,0)" flat>
        <v-btn icon href="AaddHome">
          <v-icon color="grey lighten-1" small>
            mdi-arrow-left-thick
          </v-icon>
        </v-btn>
        <v-toolber-title class="black--text">
          profile
        </v-toolber-title>
        <v-spacer />
        <v-btn icon>
          <v-icon color="grey lighten-1" normal>
            mdi-dots-vertical
          </v-icon>
        </v-btn>
      </v-toolbar>
    </v-sheet>
    <center>
      <v-card
        class="py-n8"
        light
        max-width="400"
        flat
      >
        <center>
          <v-list-item-avatar color="grey darken-3" size="70" class="pb-n8">
            <v-img
              class="elevation-6"
              alt=""
              src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light"
            />
          </v-list-item-avatar>
        </center>
        <div class="text-subtitle-1">
          <p class="text-center">
            สมศรี สมหมาย
          </p>
        </div>
        <v-card-title>
          <v-icon
            large
            left
          >
            mdi-check-circle
          </v-icon>
          <span class="text-h6 font-weight-light">ความสืบหน้า</span>
          <v-spacer />
          <v-progress-circular
            :rotate="-90"
            :value="50"
            :size="50"
            :width="15"
            color="green"
          />
        </v-card-title>
      </v-card>
    </center>
    <v-list subheader two-line class="mt-6" light>
      <v-list-item v-for="file in files" :key="file.title">
        <v-list-item-action>
          <v-icon :class="file.color" dark normal v-text="file.icon " />
        </v-list-item-action>
        <v-list-item-content>
          <v-list-item-title v-text="file.title" />
          <v-list-item-subtitle v-text="file.subtitle" />
        </v-list-item-content>
        <v-list-item-action>
          <v-btn icon>
            <v-icon color="grey lighten-1" small>
              mdi-arrow-right-thick
            </v-icon>
          </v-btn>
        </v-list-item-action>
      </v-list-item>
    </v-list>
    <div class="">
      <v-btn block dark absolute bottom href="/">
        Logout
      </v-btn>
    </div>
  </v-app>
</template>

<script>

export default {
  data: () => ({
    files: [
      {
        color: 'blue--text',
        icon: 'mdi-account-circle',
        subtitle: 'Personal information',
        title: 'ข้อมูลส่วนตัว'
      },
      {
        color: 'green--text',
        icon: 'mdi-calendar',
        subtitle: 'My activity',
        title: 'กิจกรรมของฉัน'
      },
      {
        color: 'yellow--text',
        icon: 'mdi-wrench',
        subtitle: 'Settings',
        title: 'การตั้งค่า'
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
</style>
