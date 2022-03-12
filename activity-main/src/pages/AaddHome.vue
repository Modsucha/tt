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
          <v-row justify="start">
            <div class="text-h5 font-weight-light pl-3">
              สวัสดีค่ะ ! {{ $route.query.id_student }}
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
                <a href="addPost" style="text-decoration: none;">
                  <v-icon class="mx-2 white--text" small>
                    mdi-chevron-double-right
                  </v-icon>
                </a>
              </v-row>
            </v-list-item>
          </v-card-actions>
        </v-img>
      </v-card>
      <br>
    </tr>
    <br> <br> <br>
    <v-row justify="end">
      <v-dialog
        v-model="dialog"
        fullscreen
        hide-overla
        transition="dialog-bottom-transition"
      >
        <template #activator="{ on, attrs }">
          <v-btn
            color="primary"
            dark
            fixed
            right
            bottom
            fab
            v-bind="attrs"
            v-on="on"
          >
            <v-icon>mdi-plus</v-icon>
          </v-btn>
        </template>
        <v-card>
          <v-toolbar
            dark
            color="primary"
          >
            <v-btn
              icon
              dark
              @click="dialog = false"
            >
              <v-icon>mdi-close</v-icon>
            </v-btn>
            <v-toolbar-title>สร้างกิจกรรม</v-toolbar-title>
            <v-spacer />
            <v-toolbar-items>
              <v-btn
                dark
                text
                @click="save"
              >
                โพสต์
              </v-btn>
            </v-toolbar-items>
          </v-toolbar>
          <v-list
            three-line
            subheader
          >
            <v-subheader>กิจกรรม</v-subheader>
            <v-list-item>
              <v-list-item-content>
                <v-list-item-subtitle>
                  <v-col
                    cols="12"
                    sm="6"
                    md="4"
                  >
                    <v-text-field
                      v-model="name_Ad"
                      label="ชื่อกิจกรรม"
                      required
                      prepend-inner-icon="mdi-newspaper"
                    />
                  </v-col>
                </v-list-item-subtitle>
                <v-list-item-subtitle>
                  <v-col
                    cols="12"
                    sm="6"
                    md="4"
                  >
                    <v-text-field
                      v-model="id_postad"
                      label="รหัสกิจกรรม"
                      required
                      prepend-inner-icon="mdi-book-multiple"
                    />
                    <v-text-field
                      v-model="num_S"
                      label="จำนวน"
                      required
                      type="text"
                      prepend-inner-icon="mdi-account-multiple"
                    />
                    <v-text-field
                      v-model="Location"
                      label="สถานที่"
                      prepend-inner-icon="mdi-map-marker"
                    />
                  </v-col>
                </v-list-item-subtitle>
                <v-list-item-subtitle>
                  <v-col
                    cols="12"
                    sm="6"
                    md="4"
                  >
                    <v-text-field
                      v-model="dataD"
                      label="วันที่กิจกรรม"
                      required
                      type="date"
                    />
                    <v-text-field
                      v-model="timeD"
                      label="วันที่เข้าลงชื่อ"
                      required
                      type="date"
                    />
                    <v-text-field
                      v-model="time_1"
                      label="ถึง"
                      required
                      type="date"
                    />
                  </v-col>
                  <v-col cols="12">
                    <v-textarea
                      v-model="conter"
                      label="เนื้อหา"
                      color="teal"
                    />
                  </v-col>
                </v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-list>
          <v-divider />
          <!-- <v-list
            three-line
            subheader
          >
            <v-subheader>General</v-subheader>
            <v-list-item>
              <v-list-item-action>
                <v-checkbox v-model="notifications" />
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title>Notifications</v-list-item-title>
                <v-list-item-subtitle>Notify me about updates to apps or games that I downloaded</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
            <v-list-item>
              <v-list-item-action>
                <v-checkbox v-model="sound" />
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title>Sound</v-list-item-title>
                <v-list-item-subtitle>Auto-update apps at any time. Data charges may apply</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
            <v-list-item>
              <v-list-item-action>
                <v-checkbox v-model="widgets" />
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title>Auto-add widgets</v-list-item-title>
                <v-list-item-subtitle>Automatically add home screen widgets</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-list> -->
        </v-card>
      </v-dialog>
    </v-row>
    <br> <br> <br>

    <v-bottom-navigation v-model="value" fixed bottom light>
      <v-btn value="recent" to="AaddHome">
        <span>Home</span>

        <v-icon>mdi-home</v-icon>
      </v-btn>

      <v-btn value="favorites">
        <span>Search</span>

        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn value="nearby" to="Aprofile">
        <span>profile</span>

        <v-icon>mdi-account</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      student: [],
      table_User: [],
      email: '',
      id_student: '',
      name_ABC: '',
      name_Ad: '',
      Location: '',
      id_postad: '',
      num_S: '',
      dataD: '',
      timeD: '',
      time_1: '',
      conter: '',
      amenities: '',
      dialog: false,
      notifications: false,
      sound: true,
      widgets: false
    }
  },
  created () {
    this.Show()
    this.MMdemo()
    this.Aname()
    this.save()
  },
  methods: {
    async Show () {
      console.log('show data')
      this.id_student = this.$route.query.id_student
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
    },
    async save () {
      if (
        this.name_Ad === '' ||
        this.dataD === '' ||
        this.timeD === '' ||
        this.time_1 === '' ||
        this.conter === '' ||
        this.Location === '' ||
        this.id_postad === '' ||
        this.num_S === ''
      ) {
        this.danger = true
        this.alt_txt = 'กรุณากรอกข้อมูล'
      } else {
        const addPost = {
          id_postad: this.id_postad,
          name_Ad: this.name_Ad,
          Location: this.Location,
          // AV_id: this.AV_id,
          num_S: this.num_S,
          dataD: this.dataD,
          timeD: this.timeD,
          time_1: this.time_1,
          conter: this.conter
        }
        console.log('addPost', addPost)
        const res = await fetch('http://localhost:7000/addPost', {
          method: 'post',
          headers: {
            'content-type': 'application/json'
          },
          body: JSON.stringify(addPost)
        })
        const data = await res.json()
        console.log('data', data.status)
        if (data.status === 'ok') {
          setTimeout(() => (location.reload()), 1000)
        }
      }
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
 .theme--dark.v-btn.v-btn--has-bg {
    bottom: 59px;
}
</style>
