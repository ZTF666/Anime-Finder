<template>
   <div>
    <v-alert class="dark secondary--text" 
     dismissible
      border="left"
      elevation="10"
      icon="mdi-alert-circle"
     >
      <center>The accuracy is not 100% , you may get some wrong anime😅 </center>
    </v-alert>
     <!-- Error Message -->
         <div>
            <v-alert
              v-model="alert"
              dismissible
              color="accent"
              border="left"
              elevation="2"
              colored-border
              icon="mdi-alert-circle"
              class="secondary--text"
            >
              Please Make Sure All The Required Fields Are Filled Out ! Thank you 🙏 .
            </v-alert>
        </div>
     <!-- Error Message -->
         <div>
            <v-alert
              v-model="erroralert"
              dismissible
              color="accent"
              border="left"
              elevation="2"
              colored-border
              icon="mdi-alert-circle"
              class="secondary--text"
            >
              {{erroralerttext}}
            </v-alert>
        </div>
    <!-- Form -->
    <v-form @submit.prevent="ProcessImage()">
      <v-container >
        <v-layout row wrap class="d-flex justify-center">
          <v-flex xs12 sm12 md6>
            <v-row class="d-flex justify-center">
              <v-col cols="12" sm="12" md="12">
                <v-text-field
                 outlined
                  auto-grow
                  label="Your Link Goes Here"
                  v-model="Input"
                  color="success"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row class="d-flex justify-center">
              <div>
                <v-col>
                  <v-btn color="secondary" @click.prevent="ProcessImage()" class="primary--text">👁️‍🗨️Process👁️‍🗨️</v-btn>
                </v-col>
              </div>
            </v-row>

          </v-flex>
        </v-layout>
      </v-container>
    </v-form>
    <!-- Output -->
    <v-card color="transparent" elevation="10">
        <v-card-title class="justify-center mt-5 success--text">Anime Name : {{data.filename}}</v-card-title>
        <v-card-title class="justify-center mt-5 success--text">Episode : {{data.episode}}</v-card-title>
        <v-card-title class="justify-center mt-5 success--text">Similarity : {{(data.similarity)*100}} %</v-card-title>
        <v-card-title class="justify-center mt-5 success--text">🔰Video🔰 </v-card-title>
        <v-card-actions class="justify-center">
            <video  :src="data.video" 
            class=" hidden-xs-only"
            autoplay="" loop="" playsinline=" "
            style="opacity: 1;" width="50%" height="50%">
            </video>
            <video  :src="data.video" 
            class="hidden-sm-and-up"
            autoplay="" loop="" playsinline=" "
            style="opacity: 1;" width="100%" height="100%">
            </video>
        </v-card-actions>
                
       
    </v-card>
   </div>
</template>

<script>


export default {
data(){
    return{
      alert:false,
      erroralert:false,
      erroralerttext:'',
      Input:null,
      data:'',
      api:'https://api.trace.moe/search?url=',
    }
},
methods:{
    async ProcessImage(){
      try {

           if(this.Input !=null){
        const res = await fetch(this.api+this.Input)
        if(res.status){
        const data = await res.json()
        this.data=data.result[0]
        }else{
            alert('not found , use another image')
        }
        }
        else{
            this.alert=true
        }
      } catch (error) {
        this.erroralerttext=error.message
         this.erroralert=true
      }
       
       
    },
 
}
}
</script>

<style>

</style>