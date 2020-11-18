<template>
  <div>
    <v-row style="margin-top:100px">
    <v-col cols="12" sm="12" md="2" ></v-col>
    <v-col cols="12" sm="12" md="8" c>
    
      <v-container grid-list-md text-xs-center>
      <v-layout row wrap>
        <v-flex xs2 cols="12" sm="12" md="10">
        <v-text-field
            label="Pincode"
            single-line
            outlined
          ></v-text-field>
       </v-flex>
       <v-flex xs8 cols="12" sm="12" md="10">
        <v-text-field
            label="Ex. "
            single-line
            outlined
          ></v-text-field>
       </v-flex>
       <v-flex xs2 cols="12" sm="12" md="2">
        <v-btn 
            block
            color="error"
            dark
            x-large
            >
              Search
            </v-btn>

       </v-flex>
     </v-layout>
</v-container>
    </v-col>
    <v-col cols="12" sm="12" md="2" ></v-col>
  </v-row>

  <v-row justify="center" align="center">
    <v-col cols="12" sm="6" md="2" > 
          <v-card class="mx-auto">
            <v-card-text align="center">
              <div >
                <v-avatar  size="100">
                  <v-img
                    lazy-src="https://picsum.photos/id/11/10/6"
                    src="https://i.imgur.com/Sdusa4U.png"
                  ></v-img>
                </v-avatar>
              </div>
              <div class="text-center">
                  <v-card-subtitle>
                      Flooring
                    </v-card-subtitle>
                </div>
            </v-card-text>
          </v-card>

    </v-col>
    <v-col cols="12" sm="6" md="2" > 
          <v-card class="mx-auto">
            <v-card-text align="center">
              <div >
                <v-avatar  size="100">
                  <v-img
                    lazy-src="https://picsum.photos/id/11/10/6"
                    src="https://i.imgur.com/FvHciRy.png"
                  ></v-img>
                </v-avatar>
              </div>
              <div class="text-center">
                  <v-card-subtitle>
                      Roofing
                    </v-card-subtitle>
                </div>
            </v-card-text>
          </v-card>
    </v-col>
    <v-col cols="12" sm="6" md="2" > 
          <v-card class="mx-auto">
            <v-card-text align="center">
              <div >
                <v-avatar  size="100">
                  <v-img
                    lazy-src="https://picsum.photos/id/11/10/6"
                      src="https://i.imgur.com/Sdusa4U.png"
                  ></v-img>
                </v-avatar>
              </div>
              <div class="text-center">
                  <v-card-subtitle>
                      Roofing
                    </v-card-subtitle>
                </div>
            </v-card-text>
          </v-card>
    </v-col>
    <v-col cols="12" sm="6" md="2" > 
          <v-card class="mx-auto">
            <v-card-text align="center">
              <div >
                <v-avatar  size="100">
                  <v-img
                    lazy-src="https://picsum.photos/id/11/10/6"
                    src="https://i.imgur.com/FvHciRy.png"
                  ></v-img>
                </v-avatar>
              </div>
              <div class="text-center">
                  <v-card-subtitle>
                      Roofing
                    </v-card-subtitle>
                </div>
            </v-card-text>
          </v-card>
    </v-col>
    <v-col cols="12" sm="6" md="2" > 
          <v-card class="mx-auto">
            <v-card-text align="center">
              <div >
                <v-avatar  size="100">
                  <v-img
                    lazy-src="https://picsum.photos/id/11/10/6"
                     src="https://i.imgur.com/Sdusa4U.png"
                  ></v-img>
                </v-avatar>
              </div>
              <div class="text-center">
                  <v-card-subtitle>
                      Roofing
                    </v-card-subtitle>
                </div>
            </v-card-text>
          </v-card>
    </v-col>
    <v-col cols="12" sm="6" md="2" > 
          <v-card class="mx-auto">
            <v-card-text align="center">
              <div >
                <v-avatar  size="100">
                  <v-img
                    lazy-src="https://picsum.photos/id/11/10/6"
                     src="https://i.imgur.com/Sdusa4U.png"
                  ></v-img>
                </v-avatar>
              </div>
              <div class="text-center">
                  <v-card-subtitle>
                      Roofing
                    </v-card-subtitle>
                </div>
            </v-card-text>
          </v-card>
    </v-col>
   
   
  </v-row>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  }
}
</script>
