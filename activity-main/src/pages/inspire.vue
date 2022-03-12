<template>
  <v-app class="fa">
    <v-card light class="my-5 py-6" flat>
      <div class="text-center ma-2 mt-16">
        <v-avatar size="100" color="blue lighten-4">
          <v-icon size="40">
            mdi-account-circle
          </v-icon>
        </v-avatar>
      </div>
      <v-form ref="form" @submit.prevent="submitHandler">
        <v-card-text>
          <!-- <v-text-field
            v-model="email"
            :rules="emailRules"
            type="email"
            label="Email"
            placeholder="Email"
            prepend-inner-icon="mdi-account-circle"
          /> -->
          <v-text-field
            v-model="id_student"
            label="เลขรหัสนักศึกษา"
            placeholder="ID"
            prepend-inner-icon="mdi-account-circle"
          />
          <v-text-field
            v-model="Password"
            :rules="passwordRules"
            :type="passwordShow? 'text':'password'"
            label="password"
            placeholder="password"
            prepend-inner-icon="mdi-lock"
            :append-icon="passwordShow ? 'mdi-eye':'mdi-eye-off'"
            @click:append="passwordShow = !passwordShow"
          />
          <v-switch label="Remember me?" color="indigo" />
        </v-card-text>
        <v-card-actions class="justify-center">
          <v-btn :loading="loading" type="submit" color="indigo" @click="Signin">
            <span class="white--text px-5">
              Login
            </span>
          </v-btn>
        </v-card-actions>
      </v-form>
    </v-card>
    <!--  <v-snackbar
      v-model="snackbar"
      top
      color="green"
    >
      เข้าสู่ระบบ
    </v-snackbar> -->
  </v-app>
</template>

<script>
export default {

  data: () => ({
    loading: false,
    snackbar: false,
    passwordShow: false,
    alt_txt: '',
    id_student: '',
    Password: '',
    passwordRules: [
      v => !!v || 'Password is required',
      v => (v && v.length <= 10) || 'password must be less than 10 characters'
    ]
    /* email: '',
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+\..+/.test(v) || 'E-mail must be valid'
    ] */
  }),
  methods: {
    submitHandler () {
      if (this.$refs.form.validate()) {
        this.loading = true
        /* setTimeout(() => {
          this.loading = false
          this.snackbar = true
        }, 3000) */
      }
    },
    async Signin () {
      const login = {
        id_student: this.id_student,
        Password: this.Password
      }
      console.log('Login')
      console.log('id_student', this.id_student)
      console.log('Password', this.Password)
      const res = await fetch('http://localhost:7000/login', {
        method: 'post',
        headers: {
          'content-type': 'application/json'
        },
        body: JSON.stringify(login)
      })
      const data = await res.json()
      console.log('data', data.status)
      console.log(data.rows[0].Status)
      if (data.status === 'ok') {
        if (data.rows[0].Status === 'user') {
          console.log('id_student=', JSON.stringify(data.rows[0].id_student))
          // window.localStorage.setItem('user', JSON.stringify(res.data.user))// แบบนี้ เก็บถาวร
          window.sessionStorage.setItem(
            'id_student',
            JSON.stringify(data.rows[0].id_student)
          ) // แบบนี้หาย เมื่อ restart หรือ ปิด  browser
          this.$router.push('/UHome?id_student=' + this.id_student)
          // setTimeout(
          //     () => ((this.dialog = false), this.$router.push('/home')),
          //     3000,
          // )
        } else if (data.rows[0].Status === 'admin') {
          console.log('id_student=', JSON.stringify(data.rows[0].id_student))
          // window.localStorage.setItem('user', JSON.stringify(res.data.user))// แบบนี้ เก็บถาวร
          window.sessionStorage.setItem(
            'id_student',
            JSON.stringify(data.rows[0].id_student)
          ) // แบบนี้หาย เมื่อ restart หรือ ปิด  browser
          // this.dialog = true
          this.$router.push('/AaddHome?id_student=' + this.id_student)
        }
      }
      if (data.Status === 'fail') { // id_student || pass ค่าว่าง
        this.id_student = ''
        this.Password = ''
        this.danger = true
        this.alt_txt = 'กรุณากรอกข้อมูลให้ครบ'
      }
      if (data.Status === 'no') { // id_student || pass ไม่ถูก
        this.id_student = ''
        this.Password = ''
        this.danger = true
        this.alt_txt = 'ไม่พบบัญชีผู้ใช้งาน'
        // this.alt_txt = 'กรุณาตรวจสอบ id_student หรือ รหัสผ่าน'
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
</style>
