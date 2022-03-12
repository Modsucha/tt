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
      <!--  <v-btn
        href="/User/form"
        color="primary"
        elevation="2"
        block
        bottom
      >
        ลงชื่อเข้าร่วม
      </v-btn> -->

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
                fab
                icon
                outlined
                v-on="on"
              >
                <v-icon> mdi-qrcode</v-icon>
              </v-btn>
            </template>
            <template #default="dialog">
              <v-card light>
                <v-toolbar
                  color="primary"
                  dark
                >
                  บาร์โค้ดกิจกรรม
                </v-toolbar>
                <v-card-text class="mt-8">
                  <v-row align="center" justify="center">
                    <v-sheet color="blue" height="200" width="200" />
                    <v-card class="text-center" flat>
                      <v-card-text class="pb-n8">
                        <b>กิจกรรมที่ 1</b> <br>
                        <b>น.ส. สมศรี สมหมาย</b><br>
                        <b>เลขประจำตัวนักศึกษา 63309010025</b>
                      </v-card-text>
                      <!-- <v-card-text class="pb-n8">
              น.ส. สมศรี สมหมาย
            </v-card-text>
            <v-card-text>
              เลขประจำตัวนักศึกษา 63309010025
            </v-card-text> -->
                    </v-card>
                  </v-row>
                </v-card-text>
                <v-card-actions class="justify-end">
                  <v-btn
                    text
                    @click="dialog.value = false"
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

<script>
export default {
  data: () => ({
    items: ['Foo', 'Bar', 'Fizz', 'Buzz']
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
