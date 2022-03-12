<template>
  <v-app class="ma-2">
    <v-card>
      <v-img
        src="https://cdn.vuetifyjs.com/images/cards/forest-art.jpg"
        gradient="to top, rgba(0,0,0,.44), rgba(0,0,0,.44)"
      >
        <v-card-text>
          <v-container class="fill-height">
            <v-row align="center">
              <v-btn icon href="./UHome">
                <v-icon color="grey lighten-1" small>
                  mdi-arrow-left-thick
                </v-icon>
              </v-btn>
              <v-row justify="end">
                <v-btn icon>
                  <v-icon color="grey lighten-1" normal>
                    mdi-dots-vertical
                  </v-icon>
                </v-btn>
              </v-row>
            </v-row>
          </v-container>
        </v-card-text>
        <v-card-text>
          <v-row justify="start">
            <div class="text-h5 font-weight-light pl-3 pt-6">
              <H4>กิจกรรมที่ 1</H4>
            </div>
            <v-row justify="end" align="center" class="mr-5 mt-6">
              <v-chip
                class="ma-2"
                color="green"
                label
                text-color="white"
              >
                <v-icon left small>
                  mdi-account
                </v-icon>
                224
              </v-chip>
            </v-row>
          </v-row><br>
          <div class="text-uppercase font-weight-light">
            <b>รหัสกิจกรรม 09001</b>
          </div>
          <div class="text-uppercase font-weight-light">
            <b>ระยะการเข้าร่วม 27 ธันวาคม ถึง 30 ธันวาคม 2565</b>
          </div>
        </v-card-text>
        <v-card-text>
          <v-layout row>
            <v-flex xs12>
              <div class="caption grey--text pb-2">
                <v-avatar size="30" color="blue lighten-4" class="mr-3 ml-2">
                  <v-icon size="20">
                    mdi-account-circle
                  </v-icon>
                </v-avatar>
                โดย  นาย ..... .......
              </div>
            </v-flex>
          </v-layout>
        </v-card-text>
      </v-img>
    </v-card>
    <v-card class="mt-3 mx-4 pt-2" flat light height="360">
      <v-card-actions class="pl-6 ml-1">
        <v-layout row>
          <v-flex xs12>
            <div class="caption grey--text">
              <v-icon left small>
                mdi-map-marker
              </v-icon>
              วิทยาลัยเทคนิคชัยภูมิ
            </div>
          </v-flex>
          <v-flex xs12>
            <div class="caption grey--text">
              <v-icon left small>
                mdi-clock
              </v-icon>
              06.00 am - 08:00 am
            </div>
          </v-flex>
          <v-flex xs12>
            <div class="caption grey--text">
              <v-icon left small>
                mdi-application
              </v-icon>
              วันที่ 30 ธันวาคม 2564
            </div>
          </v-flex>
          <v-flex xs12>
            <div class="caption grey--text">
              <v-icon left small>
                mdi-account-multiple
              </v-icon>
              ไม่จำกัดนักเรียนนักศึกษา
            </div>
          </v-flex>
          <v-flex xs12>
            <div class="caption grey--text py-2">
              งานกิจรรมนักเรียน นักศึกษา..
              งานกิจกรรมฯ ขอเรียนเชิญคณะครู เจ้าหน้าที่ บุคลากรทางการศึกษา และนักเรียน นักศึกษา ร่วมงานวันคล้ายวันสถาปนาวิทยาลัยเทคนิคชัยภูมิ ครบรอบ 83 ปี (20 ธันวาคม) ในวันที่ 30 ธันวาคม 2564 ตามกิจกรรมดังนี้
              -เวลา 06.00 น. พิธีบวงสรวง ณ ลานหน้าศาลเจ้าพ่อพญาแล ภายในวิทยาลัยเทคนิคชัยภูมิ
              -เวลา 08.00 น. พิธีสงฆ์ ณ เวทีโดมหน้าเสาธง
              -สำหรับนักเรียน นักศึกษา เป็นกิจกรรมพิเศษ
            </div>
          </v-flex>
        </v-layout>
      </v-card-actions>
      <div class="py-3" />
      <v-row justify="space-around">
        <v-col cols="auto">
          <v-dialog
            transition="dialog-bottom-transition"
            max-width="600"
          >
            <template #activator="{ on, attrs }">
              <v-btn
                color="primary"
                v-bind="attrs"
                block
                v-on="on"
              >
                ลงทะเบียน
              </v-btn>
            </template>
            <template #default="dialog">
              <v-card light>
                <v-toolbar
                  color="primary"
                  dark
                >
                  ลงชื่อเข้าร่วม
                </v-toolbar>
                <v-card-text>
                  <v-col
                    cols="12"
                  >
                    <v-form class="form">
                      <v-text-field
                        v-model="id_postad"
                        class="form-control"
                        label="รหัสกิจกรรม"
                        outlined
                        light
                      />
                      <v-text-field
                        v-model="id_student"
                        class="form-control"
                        label="รหัสประจำตัวนักศึกษา"
                        outlined
                        light
                      />
                    </v-form>
                  </v-col>
                </v-card-text>
                <!-- <v-sheet color="blue" height="200" width="200">
                  <div>
                    <img src="<%=src%"> alt="QR Code Image" >
                    <p>Scan the QR Code to access data!</p>
                  </div>
                </v-sheet> -->
                <v-card-actions class="justify-end">
                  <v-btn
                    type="submit"
                    text
                    @click="dialog.value = true"
                  >
                    ตกลง
                  </v-btn>
                </v-card-actions>
              </v-card>
            </template>
          </v-dialog>
        </v-col>
      </v-row>
    </v-card>
  </v-app>
</template>

<style>
.btm {
        position: absolute;
        bottom: 0;
    }
.text__1{
  font-size: 12px;
}
div p{
  font-size: 10px;

}
</style>
<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&family=Sarabun:wght@200&display=swap');

 .fa{
   font-family: 'Open Sans';
   font-family: 'Sarabun', sans-serif;
 }
</style>

<script >

export default ({
  data: () => ({
    student: [],
    table_User: [],
    id_student: '',
    id_postad: ''
  }),
  created () {
    this.Show()
    this.MMdemo()
    this.Aname()
    this.A_name()
    this.Scan()
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
    },
    async A_name () {
      this.id_postad = this.$route.query.id_postad
      const res = await fetch('http://localhost:7000/list?id_postad=' + this.id_postad)
      const data = await res.json()
      this.name_ABC = data.rows[0][0].name_ABC
      this.dataD = data.rows[0][0].dataD
      this.timeD = data.rows[0][0].timeD
      this.time_1 = data.rows[0][0].time_1
      this.conter = data.rows[0][0].conter
      this.Location = data.rows[0][0].Location
      this.num_S = data.rows[0][0].num_S
    },
    // คิวอาร์โค้ด
    async Scan () {
      const avtivi = {
        id_student: this.id_student,
        id_postad: this.id_postad
      }
      console.log('avtivi')
      console.log('id_student', this.id_student)
      console.log('id_postad', this.id_postad)
      const res = await fetch('http://localhost:7000/avtivi', {
        method: 'post',
        headers: {
          'content-type': 'application/json'
        },
        body: JSON.stringify(avtivi)
      })
      const body = await res.json()
      this.id_student = body.rows[0][0].id_student
      this.Password = body.rows[0][0].Password
    },
    async submit () {
      console.log('show data')
      const res = await fetch('http://localhost:7000/avtivities?id=' + this.id_postad) // const ประกาศตัวแปร
      const data = await res.json()
      this.student = data.rows[0]
      console.log(data.rows[0])
    }
  }
})
</script>
