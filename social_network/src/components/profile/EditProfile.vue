<template>
  <v-container>
    <v-form ref="form" lazy-validation v-if="ownerprofile">
      
        <v-row>
          <v-col cols="12" md="4">
            <v-text-field
              v-model="profile.workplace"
              label="Work Place"
              required
            ></v-text-field>
          </v-col>

          <v-col cols="12" md="4">
            <v-text-field
              v-model="profile.currentcity"
              label="Current City"
              required
            ></v-text-field>
          </v-col>

          <v-col cols="12" md="4">
            <v-text-field
              v-model="profile.hometown"
              label="Home Town"
              required
            ></v-text-field>
          </v-col>
        </v-row>

      <v-content class="content-bar pa-1">
        <v-icon left>fas fa-graduation-cap</v-icon>
        <span>Education</span>
      </v-content>

      <v-row>
        <v-col cols="12" md="4">
          <v-text-field
            v-model="profile.primeryschool"
            label="Primery School"
            required
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="4">
          <v-text-field
            v-model="profile.secondaryschool"
            label="Secondary School"
            required
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="4">
          <v-text-field
            v-model="profile.university"
            label="University"
            required
          ></v-text-field>
        </v-col>
      </v-row>

      <v-content class="content-bar pa-1">
        <v-icon left>fas fa-user-tie</v-icon>
        <span>Basic Info</span>
      </v-content>

      <v-row>
        <v-col cols="12" md="6">
          <v-text-field
            v-model="profile.birthday"
            label="Birth Day"
            required
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="4">
          <v-text-field
            v-model="profile.religious"
            label="Religious"
            required
          ></v-text-field>
        </v-col>
      </v-row>

      <v-row>
        <v-col cols="12" md="6">
          <v-text-field
            v-model="profile.gender"
            label="Gender"
            required
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="4">
          <v-text-field
            v-model="profile.sivilstatus"
            label="Sivil Status"
            required
          ></v-text-field>
        </v-col>
      </v-row>

      <v-content class="content-bar pa-1">
        <span>ADD SKILL</span>
      </v-content>

      <v-row>
        <v-col cols="12" md="12">
          <v-text-field
            v-model="profile.skills"
            label="Skills"
            required
          ></v-text-field>
        </v-col>
      </v-row>
      <v-btn block color="primary" dark @click="editProfile">Save Changes</v-btn>
    
  </v-form>
  </v-container>
</template>
    
<script>

import {mapActions,mapGetters} from 'vuex';
export default {
    name:"EditProfile",
    data (){
       return{
           profile:{}
          // workplace:''
       }
    },
    computed:{
        ...mapGetters(['ownerprofile'])
    },
    methods:{
    ...mapActions(['createProfile','fetchOwnerProfile']),
    editProfile: function(){
         let data = {
             workplace:this.profile.workplace,
             currentcity:this.profile.currentcity,
             hometown:this.profile.hometown,
             primeryschool:this.profile.primeryschool,
             secondaryschool:this.profile.secondaryschool,
             university:this.profile.university,
             birthday:this.profile.birthday,
             religious:this.profile.religious,
             gender:this.profile.gender,
             sivilstatus:this.profile.sivilstatus,
             skills:this.profile.skills
        }
      console.log(data);
      this.createProfile(data);
    }  
    },
    created(){
        this.fetchOwnerProfile();
        
    },
    updated(){
      // this.workplace = this.ownerprofile.workplace;
      this.profile = this.ownerprofile
    }
}
</script>

<style scoped>
  .content-bar{
    border: 2px solid grey;
    text-align: center;
    border-radius: 2px;
  }
</style>