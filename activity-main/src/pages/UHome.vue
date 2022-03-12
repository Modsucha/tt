<template>
  <v-app id="Home" class="ma-2 fa">
    <v-card>
      <v-img
        src="https://cdn.vuetifyjs.com/images/cards/forest-art.jpg"
        gradient="to top, rgba(0,0,0,.44), rgba(0,0,0,.44)"
      >
        <v-card-text>
          <v-container class="fill-height">
            <v-row align="center">
              <v-avatar size="45px">
                <a href="username" style="text-decoration: none;"><img src="https://i.pravatar.cc/64"></a>
              </v-avatar>
              <v-row justify="end">
                <v-badge color="#41AB55" overlap content="3" class="mr-2">
                  <v-avatar color="#ECF7EE" size="40">
                    <a href="warn" style="text-decoration: none;">
                      <v-icon color="#41AB55" size="17">
                        mdi-bell
                      </v-icon>
                    </a>
                  </v-avatar>
                </v-badge>
              </v-row>
            </v-row>
          </v-container>
        </v-card-text>
        <v-card-text>
          <!--      <tr v-for="st in student" :key="st.id_postad">
      <td>{{ st.name_Ad }}</td>
      <td>{{ st.Location }}</td>
      <td>{{ st.dataD }}</td>
      <td>{{ st.timeD }}</td>
      <td>{{ st.time_1 }}</td>
      <td>{{ st.conter }}</td>
    </tr> -->
          <v-row justify="start">
            <div class="text-h5 font-weight-light pl-3">
              สวัสดีค่ะ !
            </div>
          </v-row><br>
          <div class="text-uppercase font-weight-light">
            คุณ {{ name_ABC }}
          </div>
        </v-card-text>
        <v-card-text>
          <v-text-field
            append-icon="mdi-microphone"
            class="mx-4"
            flat
            hide-details
            label="Search"
            prepend-inner-icon="mdi-magnify"
            solo-inverted
          />
        </v-card-text>
      </v-img>
    </v-card>
    <!-- <v-img
      src="https://cdn.vuetifyjs.com/images/cards/forest.jpg"
      gradient="to top, rgba(0,0,0,.44), rgba(0,0,0,.44)"
    >
      <v-container class="fill-height">
        <v-row align="center">
          <strong class="text-h1 font-weight-regular mr-6">8</strong>
          <v-row justify="end">
            <div class="text-h5 font-weight-light">
              Monday
            </div>
            <div class="text-uppercase font-weight-light">
              February 2015
            </div>
          </v-row>
        </v-row>
      </v-container>
    </v-img> -->
    <!-- ตัวเลือก -->
    <v-card light flat>
      <v-card-text>
        <h2 class="text-h6 mb-2">
          แท็กนิยม
        </h2>

        <v-chip-group
          v-model="amenities"
          column
          multiple
          active-class="primary--text"
        >
          <v-chip
            filter
            outlined
          >
            #กิจกรรมลูกเสือ
          </v-chip>
          <v-chip
            filter
            outlined
          >
            #กิจกรรมวันพ่อ
          </v-chip>
          <v-chip
            filter
            outlined
          >
            #กิจกรรมวันสำคัญ
          </v-chip>
          <v-chip
            filter
            outlined
          >
            #กิจกรรมวันแม่
          </v-chip>
          <v-chip
            filter
            outlined
          >
            #สมาสบอยสมาสเกริด
          </v-chip>
        </v-chip-group>
      </v-card-text>
    </v-card>
    <!-- กิจกรรม -->
    <tr v-for="st in student" :key="st.id_postad">
      <v-card light>
        <v-img
          src="https://cdn.vuetifyjs.com/images/cards/forest-art.jpg"
          gradient="to top, rgba(0,0,0,.44), rgba(0,0,0,.44)"
          height="200"
        >
          <v-card-title>
            <span class="text-h6 font-weight-light white--text"><b>{{ st.name_Ad }}</b></span>
            <v-row justify="end">
              <v-btn icon>
                <v-icon color="grey lighten-1" normal>
                  mdi-dots-vertical
                </v-icon>
              </v-btn>
            </v-row>
          </v-card-title>
          <v-card-text class="white--text">
            {{ st.Location }} <br>  ระยะการเข้าร่วม {{ st.timeD }} ถึง {{ st.time_1 }}
          </v-card-text>
          <v-card-actions class="mt-n3">
            <v-list-item>
              <div color="grey lighten-3">
                <v-avatar class="ml-n3" size="30">
                  <img src="@/assets/img/ดาวน์โหลด (2).jpg" alt="">
                </v-avatar>
                <v-avatar class="ml-n3" size="30">
                  <img src="@/assets/img/56 (1).jpg" alt="">
                </v-avatar>
                <v-avatar class="ml-n3" size="30">
                  <img src="@/assets/img/ดาวน์โหลด (2).jpg" alt="">
                </v-avatar>
                <v-avatar class="ml-n3" size="30" color="black">
                  <span class="caption white--text">+220</span>
                </v-avatar>
              </div>
              <v-row align="end" justify="end">
                <v-icon class="mr-1 white--text" small>
                  mdi-account
                </v-icon>

                <span class="caption white--text">223</span>
                <!-- <router-link :to="{ path: '/U_avtivities?id_student='+id_student+'/id_postad='+st.id_postad, params: { id_student: id_student , id_postad:st.id_postad}}"> -->
                <router-link :to="{ path: '/U_avtivities?id_student='+id_student, params: { id_student: id_student , id_postad:st.id_postad}}">
                  <!-- <router-link :to="{ path: '/U_avtivities/:id_student/:id_postad', params: { id_student: id_student , id_postad:st.id_postad}}"> -->
                  <v-icon btn class="mx-2 white--text" small>
                    mdi-chevron-double-right
                  </v-icon>
                </router-link>
              </v-row>
            </v-list-item>
          </v-card-actions>
        </v-img>
      </v-card>
      <br>
    </tr>
    <br> <br> <br>

    <v-bottom-navigation v-model="value" fixed bottom light>
      <v-btn value="recent" to="./UHome">
        <span>Home</span>

        <v-icon>mdi-home</v-icon>
      </v-btn>

      <v-btn value="favorites">
        <span>Search</span>

        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <!-- <router-link :to="{ path: '/U_avtivities?id_student='+id_student, params: { id_student: id_student , id_postad:st.id_postad}}"> -->

      <!-- <v-btn value="nearby" icon color="#FF0000" :to="{ path: '/Uprofile?id_student='+id_student , params: { id_student: id_student}}">
        <v-icon>mdi-account circle</v-icon>
      </v-btn> -->
      <v-btn value="nearby" icon color="#FF0000" :to="{ path: '/Uprofile?id_student='+id_student , params: { id_student: id_student}}">
        <span>profile</span>

        <v-icon>mdi-account</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
export default {
  name: 'Home',
  data: () => ({
    student: [],
    table_User: [],
    name_ABC: '',
    email: '',
    id_student: '',
    value: '',
    amenities: [1, 4],
    files: [
      {
        color: 'blue--text',
        icon: 'mdi-account-circle',
        subtitle: 'Personal information',
        title: 'ข้อมูลส่วนตัว'
      }
    ]
  }),
  created () {
    this.Show()
    this.MMdemo()
    this.Aname()
  },
  methods: {
    async Show () {
      console.log('show data')
      const res = await fetch('http://localhost:7000/list') // const ประกาศตัวแปร
      const data = await res.json()
      this.student = data.rows[0]
      console.log(data.rows[0])
    },
    async MMdemo () {
      console.log('show data')
      const res = await fetch('http://localhost:7000/User_demo') // const ประกาศตัวแปร
      const data = await res.json()
      this.table_User = data.rows[0]
      console.log(data.rows[0])
    },
    async Aname () {
      this.id_student = this.$route.query.id_student
      const res = await fetch('http://localhost:7000/logUser?id_student=' + this.id_student)
      const data = await res.json()
      this.id_student = data.rows[0][0].id_student
      this.Password = data.rows[0][0].Password
      this.email = data.rows[0][0].email
      this.ID = data.rows[0][0].ID
      this.name_ABC = data.rows[0][0].name_ABC
      this.Status = data.rows[0][0].Status
    }
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&family=Sarabun:wght@200&display=swap');

 .fa{
   font-family: 'Open Sans';
   font-family: 'Sarabun', sans-serif;
 }
</style>
