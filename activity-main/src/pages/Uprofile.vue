<template>
  <v-app class="ma-2 fa">
    <v-sheet height="50" light>
      <v-toolbar color="rgba(0,0,0,0)" flat>
        <v-btn icon href="UHome">
          <v-icon color="grey lighten-1" small>
            mdi-arrow-left-thick
          </v-icon>
        </v-btn>
        <v-toolber-title class="black--text">
          Profile
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
            {{ name_ABC }} {{ l_name }}
            {{ Password }}
            {{ email }}
            {{ Status }}
            <v-dialog
              v-model="dialog"
              persistent
              max-width="600px"
            >
              <template #activator="{ on, attrs }">
                <v-btn
                  color="primary"
                  dark
                  v-bind="attrs"
                  outlined
                  rounded
                  x-small
                  v-on="on"
                >
                  <v-icon size="10">
                    mdi-pencil
                  </v-icon>
                </v-btn>
              </template>
              <v-card>
                <v-card-title>
                  <span class="text-h5">User Profile</span>
                </v-card-title>
                <v-card-text>
                  <v-container>
                    <v-row>
                      <v-col
                        cols="12"
                        sm="6"
                        md="4"
                      >
                        <v-text-field
                          label="Legal first name*"
                          required
                        />
                      </v-col>
                      <v-col
                        cols="12"
                        sm="6"
                        md="4"
                      >
                        <v-text-field
                          label="Legal middle name"
                          hint="example of helper text only on focus"
                        />
                      </v-col>
                      <v-col
                        cols="12"
                        sm="6"
                        md="4"
                      >
                        <v-text-field
                          label="Legal last name*"
                          hint="example of persistent helper text"
                          persistent-hint
                          required
                        />
                      </v-col>
                      <v-col cols="12">
                        <v-text-field
                          label="Email*"
                          required
                        />
                      </v-col>
                      <v-col cols="12">
                        <v-text-field
                          label="Password*"
                          type="password"
                          required
                        />
                      </v-col>
                      <v-col
                        cols="12"
                        sm="6"
                      >
                        <v-select
                          :items="['0-17', '18-29', '30-54', '54+']"
                          label="Age*"
                          required
                        />
                      </v-col>
                      <v-col
                        cols="12"
                        sm="6"
                      >
                        <v-autocomplete
                          :items="['Skiing', 'Ice hockey', 'Soccer', 'Basketball', 'Hockey', 'Reading', 'Writing', 'Coding', 'Basejump']"
                          label="Interests"
                          multiple
                        />
                      </v-col>
                    </v-row>
                  </v-container>
                  <small>*indicates required field</small>
                </v-card-text>
                <v-card-actions>
                  <v-spacer />
                  <v-btn
                    color="blue darken-1"
                    text
                    @click="dialog = false"
                  >
                    Close
                  </v-btn>
                  <v-btn
                    color="blue darken-1"
                    text
                    @click="dialog = false"
                  >
                    Save
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-dialog>
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
      <v-btn
        block
        dark
        absolute
        bottom
        href="/"
      >
        Logout
      </v-btn>
    </div>
  </v-app>
</template>

<script>

export default {
  data: () => ({
    student: [],
    id_student: '',
    Password: '',
    email: '',
    name_ABC: '',
    l_name: '',
    Status: '',
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
  }),
  created () {
    this.Aname()
    // this.initialize()
    // const res1 = await fetch('http://localhost:7000/table_user')
    // const data1 = await res1.json()
    // console.log('desserts', data1.rows[0])
    // this.desserts = data1.rows[0]

    this.id_student = this.$route.query.id_student
    // this.ID = this.$route.params.ID
  },
  methods: {
    async MMdemo () {
      console.log('show data')
      const res = await fetch('http://localhost:7000/logProfile') // const ประกาศตัวแปร
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
      this.name_ABC = data.rows[0][0].name_ABC
      this.l_name = data.rows[0][0].l_name
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
