<template>
<div data-app class="ss">
    <!-- <div data-app style="background-color:powderblue;"> -->
    <v-container fluid style="margin: 0px; padding: 0px; width: 100%">
        <v-layout wrap>
            <v-app-bar color="#FFC400" class="" dark>
                <v-btn icon color="#FF0000" :to="{ name: 'profile' , params: { ID_student: ID_student}}">
                    <v-icon>mdi-account circle</v-icon>
                </v-btn>

                <v-toolbar-title class="white--text" style="white">| หน้าหลัก </v-toolbar-title>
                <v-spacer></v-spacer>
                <v-btn icon @click="logout" color="#FF0000">
                    <v-icon>mdi-logout</v-icon>
                </v-btn>
            </v-app-bar>

            <v-container class="grey lighten-5">
                <!-- <v-img lazy-src="https://picsum.photos/id/11/10/6" max-height="150" max-width="500" src="https://picsum.photos/id/11/500/300"></v-img> -->
                <!-- <v-img lazy-src="https://cdn.chiangmainews.co.th/wp-content/uploads/2020/07/04170055/S__12951581-scaled.jpg" max-height="180" max-width="500" src="http://www.stc.ac.th/files/2009120990337274_2011180660231.jpg"></v-img> -->
                <!-- <v-img max-height="180" max-width="400" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQvVEd5Y0g8lCYFiiCDfeVErgLRw2MHAvQuh3_L0nKcaHSTD3QKUN7g7zhk0FG01Cmuvvc&usqp=CAU"></v-img> -->
            </v-container>

            <v-col class="pb-0 pt-0">
                <!-- <v-btn @click.prevent="Signin" type="submit" color="#1F7087" block dark>เช็คชื่อ</v-btn> -->
                <!-- <v-btn @click.prevent="Signin" type="submit" color="#952175" class="mt-2 " block dark>อัลบั้มภาพกิจกรรม ลูกเสือ/รด.</v-btn> -->
                <v-btn :to="{ name: 'checkAc' , params: { ID_student: ID_student}}" type="submit" color="#FF0000" class="mt-0 " block dark>เช็คกิจกรรม</v-btn>
                <!-- <v-btn :to="{ name: 'checkAc' , params: { ID_student: ID_student}}" dark class="btn-muted sm" outlined rounded small>

                    <v-btn @click.prevent="Signin" type="submit" color="#FF0000" class="mt-0 " block dark>เช็คกิจกรรม</v-btn>

                </v-btn> -->
                <center>
                    <hr style="height:2px; width:15%" color=#FF0000>
                </center>
            </v-col>

            <v-container class="pt-0">
                <v-row dense>

                    <v-col class="pb-1 font-weight-bold">
                        <!-- <h5> &nbsp;&nbsp;กิจกรรม</h5> -->
                        <h4 class="font-weight-bold pt-0 " align="left" justify="left" dark>
                            <v-btn icon color="#FF0000" @click="ac2">
                                <v-icon>mdi-dialpad</v-icon>
                            </v-btn>
                            กิจกรรมลูกเสือ - รด.
                        </h4>

                        <!-- <h4 class="font-weight-bold pt-0 " align="center" justify="center" dark>
                            กิจกรรม
                        </h4> -->
                    </v-col>

                    <v-col v-for="(item) in items" :key="item.ID" cols="12">
                        <v-card color="#E0E0E0" dark height="105">
                            <div class="d-flex flex-no-wrap justify-space-between text-dark ">
                                <v-avatar class="" size="105" tile>
                                    <v-img :src="item.src"></v-img>
                                </v-avatar>
                                <div>
                                    <h6 class="text-h6 pt-2 pb-0 pl-3" v-text="item.title"></h6>

                                    <!-- <v-card-subtitle v-text="item.artist"></v-card-subtitle> -->

                                    <h6 class="ml-3 pt-0 pb-0">...</h6>
                                    <small v-text="item.artist" class="pl-3 mb-0"></small>
                                    <!-- <v-btn dark class="btn-muted sm ml-1" @click="editStudent(post.name_coin,ID )" outlined rounded small>

                                    </v-btn> -->
                                    <!-- &nbsp;&nbsp; -->

                                    <v-dialog :v-model="dialog" width="500">
                                        <template v-slot:activator="{ on, attrs }">
                                            <v-btn dark v-bind="attrs" v-on="on" class="btn-muted sm ml-5" align="right" color=#FF0000 justify="right" @click="see" outlined rounded small>
                                                ดูเพิ่มเติม<v-icon small>mdi-chevron-right</v-icon>
                                            </v-btn>
                                        </template>

                                        <v-card>
                                            <v-card-title style="color: black; background: #e3e5f1;">
                                                {{ item.title }}
                                            </v-card-title>
                                            <v-card-text style="color: black; background: #e3e5f1;">
                                                <center>
                                                    <br>
                                                    <v-avatar class="mb-3" width="250" height="150" tile>
                                                        <v-img :src="item.src"></v-img>
                                                    </v-avatar>
                                                    <br>

                                                    <span class="pt-2"> Lorem ipsum dolor, sit amet consectetur adipisicing elit. Fuga quae, ab maxime eos quos voluptas reprehenderit praesentium. Quis, doloremque animi nulla quod aperiam aliquid earum voluptatibus dolor aut commodi nobis.</span>
                                                    <br>
                                                    <p class="mt-2 mb-0">วันที่ : {{ item.artist }}</p>
                                                    <p class="mt-1">ณ วิทยาลัยเทคนิคชัยภูมิ</p>
                                                </center>
                                            </v-card-text>
                                        </v-card>
                                    </v-dialog>
                                </div>

                            </div>
                        </v-card>
                    </v-col>

                </v-row>
            </v-container>
        </v-layout>
    </v-container>

    <v-card max-width="400" class="mx-auto" fluid>

    </v-card>
</div>
</template>

<script>
/* eslint-disable */
import addCoin from '../components/addCoin.vue'
import axios from 'axios'

export default {
    name: 'home',
    data: () => ({
        ID: '',
        ID_student: '',
        email: '',
        name: '',
        Password: '',
        Status: '',
        numm: '',

        model: null,

        name_coins: '',
        tickets: [],

        dialog: false,
        dialog1: false,
        list_coin: [],
        list_coin2: [],

        search: '',
        items: [{
                color: '#1F7087',
                src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ75gy3VVt6vIo4nx0jbjB97O6sc95YQHpMP6fl82LcqKGy9Gg3w8h-RpshCLcca4S4x5E&usqp=CAU',
                title: 'กิจกรรมเดินสนาม',
                artist: '20 พ.ค. 65',
                ID: 1
            },
            {
                color: '#952175',
                src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRc2LrwdJuERyjrlodDiqkUm61mFLcgwXUPlg&usqp=CAU',
                title: 'พิธีประจำการลูกเสือ เนตรนารี ',
                artist: '20 พ.ค. 65',
                ID: 2
            },
            {
                color: '#952175',
                src: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSXsHEUYJgF-CqfpKnyU8E3WOqprGUCQxzIrw&usqp=CAU',
                title: 'กิจกรรมเข้าค่ายลูกเสือ',
                artist: '20 พ.ค. 65',
                ID: 3
            },
            {
                color: '#952175',
                src: 'https://i.ytimg.com/vi/MgtN3eNKjRw/maxresdefault.jpg',
                title: 'กิจกรรมเดินทางไกล',
                artist: '20 พ.ค. 65',
                ID: 4
            },
        ],

        length: 3,
        onboarding: 0,

    }),
    mounted() {
        axios.get('https://api.bitkub.com/api/market/symbols')
            .then((a) => {
                this.tickets = a.data.result
                // console.log(a.data.result)
            })
    },
    components: {
        addCoin
    },
    async created() {
        if (!window.sessionStorage.getItem('ID_student')) {
            // this.dialog1 = true
            // setTimeout(() => (this.dialog1 = false, this.$router.push('/')), 2000)
        } else {
            let ID_student = window.sessionStorage.getItem('ID_student')
            let res = await fetch('http://localhost:7000/logUser?ID_student=' + ID_student)
            let data = await res.json()
            this.ID_student = data.rows[0][0].ID_student
            this.Password = data.rows[0][0].Password
            this.Title = data.rows[0][0].Title
            this.Firstname = data.rows[0][0].Firstname
            this.Lastname = data.rows[0][0].Lastname
            this.Class = data.rows[0][0].Class
            this.Department = data.rows[0][0].Department

            console.log('data', data.rows[0][0])

        }
    },
    methods: {
        logout() {
            window.sessionStorage.removeItem('ID_student')
            return this.$router.push('/')
        },

        next() {
            this.onboarding = this.onboarding + 1 === this.length ?
                0 :
                this.onboarding + 1
        },
        prev() {
            this.onboarding = this.onboarding - 1 < 0 ?
                this.length - 1 :
                this.onboarding - 1
        },
        ac2() {
            this.$router.push('Proflie')
        },
        see() {
            this.dialog = true
        },
        see2() {
            this.dialog = false
        },
    },
}
</script>

<style scoped>
.ss {
    /* background-color: #cccccc;
    width: 100% */
}
</style>
