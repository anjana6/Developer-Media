<template>
    <v-container>
        <v-content >
            <v-layout row m-5 class="pro-header">
                <v-flex xs4>
                    profile Image
                </v-flex>
                <v-flex xs8>
                    <h1 class="display-3 ma-5">{{ownerprofile.user.name}}</h1>
                </v-flex>
            </v-layout>
        </v-content>
       <v-content>
         <v-layout row>
            <v-flex md4 v-if="ownerprofile.workplace">
                <v-banner two-line>
                    <v-avatar slot="icon" color="primary accent-4" size="40">
                    <v-icon color="white">fas fa-briefcase</v-icon>
                    </v-avatar>
                        {{ownerprofile.workplace}}<br><span class="grey--text caption">Work Palce</span>
                </v-banner>
            </v-flex>
            <v-flex md4>
                <v-banner two-line>
                    <v-avatar slot="icon" color="primary accent-4" size="40">
                    <v-icon color="white">fas fa-home</v-icon>
                    </v-avatar>
                        {{ownerprofile.currentcity}}<br><span class="grey--text caption">Current City</span>
                </v-banner>
            </v-flex>
            <v-flex md4>
                <v-banner two-line>
                    <v-avatar slot="icon" color="primary accent-4" size="40">
                    <v-icon color="white">fas fa-map-marker-alt</v-icon>
                    </v-avatar>
                        {{ownerprofile.hometown}}<br><span class="grey--text caption">Home Town</span>
                </v-banner>
            </v-flex>
         </v-layout>
       </v-content>
       <v-content>
        <h2>Education</h2>
         <v-layout row>
            <v-flex md6 v-if="ownerprofile.primeryschool">
                <v-banner two-line>
                    <v-avatar slot="icon" color="primary accent-4" size="40">
                    <v-icon color="white">fas fa-graduation-cap</v-icon>
                    </v-avatar>
                        {{ownerprofile.primeryschool}}<br><span class="grey--text caption">Primery School</span>
                </v-banner>
            </v-flex>
            <v-flex md6>
                <v-banner two-line>
                    <v-avatar slot="icon" color="primary accent-4" size="40">
                    <v-icon color="white">fas fa-graduation-cap</v-icon>
                    </v-avatar>
                        {{ownerprofile.secondaryschool}}<br><span class="grey--text caption">Secondary School</span>
                </v-banner>
            </v-flex>
            <v-flex md6 v-if="ownerprofile.university">
                <v-banner two-line>
                    <v-avatar slot="icon" color="primary accent-4" size="40">
                    <v-icon color="white">fas fa-graduation-cap</v-icon>
                    </v-avatar>
                        {{ownerprofile.university}}<br><span class="grey--text caption">University</span>
                </v-banner>
            </v-flex>
         </v-layout>
       </v-content>
        <v-content>
        <h2>Basic Info</h2>
         <v-layout row>
            <v-flex md6 v-if="ownerprofile.birthday">
                <v-banner two-line>
                    <v-avatar slot="icon" color="primary accent-4" size="40">
                    <v-icon color="white">fas fa-birthday-cake</v-icon>
                    </v-avatar>
                        {{ownerprofile.birthday}}<br><span class="grey--text caption">BirthDay</span>
                </v-banner>
            </v-flex>
            <v-flex md6 v-if="ownerprofile.religious">
                <v-banner two-line>
                    <v-avatar slot="icon" color="primary accent-4" size="40">
                    <v-icon color="white">fas fa-map-marker-alt</v-icon>
                    </v-avatar>
                        {{ownerprofile.religious}}<br><span class="grey--text caption">Religious</span>
                </v-banner>
            </v-flex>
            <v-flex md6 v-if="ownerprofile.gender">
                <v-banner two-line>
                    <v-avatar slot="icon" color="primary accent-4" size="40">
                    <v-icon color="white">fas fa-user</v-icon>
                    </v-avatar>
                        {{ownerprofile.gender}}<br><span class="grey--text caption">Gender</span>
                </v-banner>
            </v-flex>
            <v-flex md6 v-if="ownerprofile.sivilstatus">
                <v-banner two-line>
                    <v-avatar slot="icon" color="primary accent-4" size="40">
                    <v-icon color="white"> fas fa-heart</v-icon>
                    </v-avatar>
                        {{ownerprofile.sivilstatus}}<br><span class="grey--text caption">sivil status</span>
                </v-banner>
            </v-flex>
         </v-layout>
       </v-content>
       <v-content v-if="!!ownerprofile.skills">
           <h2>Skills</h2>
           <v-layout row >
                
              <v-flex v-for="skill in ownerprofile.skills" :key="skill.id" md-3>
                <v-banner two-line>
                    <v-icon size="15" > fa fa-bullseye</v-icon>
                    {{skill}}
                </v-banner>
              </v-flex>
           </v-layout>
       </v-content>
       <!-- <v-content v-if="!!profile.skills">
           <h2>Skills</h2>
           <v-layout row >
                
              <v-flex v-for="skill in profile.skills" :key="skill.id" md-3>
                <v-banner two-line>
                    <v-icon size="15" > fa fa-bullseye</v-icon>
                    {{skill}}
                </v-banner>
              </v-flex>
           </v-layout>
       </v-content> -->
    <v-btn class="ma-2" block tile outlined color="secondary" to="/editprofile">
      <v-icon left>mdi-pencil</v-icon> Edit Details
    </v-btn>
    </v-container>
</template>

<script>
// import {mapActions,mapGetters} from 'vuex';
export default {
    name:'Profile',
    props:['ownerprofile'],
    // computed:{
    //     ...mapGetters(['ownerprofile','isProfile'])
    // },
    // methods:{
    //     ...mapActions(['fetchOwnerProfile'])
    // },
    // created(){
    //     this.fetchOwnerProfile()
    // }

}
</script>

<style  scoped>
    .pro-header{
        border: 1px solid black;
        align-items: center;
    }
</style>