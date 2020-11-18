<template>
    <div>
        <v-row>
              <v-col cols="12" sm="6" md="4" >
                  <v-card
                        class="mx-auto"
                        max-width="434"
                        tile
                    >
                        <v-img
                        height="100%"
                        src="https://cdn.vuetifyjs.com/images/cards/server-room.jpg"
                        >
                        <v-row
                            align="end"
                            class="fill-height"
                        >
                            <v-col
                            align-self="start"
                            class="pa-0"
                            cols="12"
                            >
                            <v-avatar
                                class="profile"
                                color="grey"
                                size="164"
                                tile
                            >
                                <v-img src="https://cdn.vuetifyjs.com/images/profiles/marcus.jpg"></v-img>
                            </v-avatar>
                            </v-col>
                            <v-col class="py-0">
                            <v-list-item
                                color="rgba(0, 0, 0, .4)"
                                dark
                            >
                                <v-list-item-content>
                                <v-list-item-title class="title">
                                    Marcus Obrien
                                </v-list-item-title>
                                <v-list-item-subtitle>Network Engineer</v-list-item-subtitle>
                                </v-list-item-content>
                            </v-list-item>
                            </v-col>
                        </v-row>
                        </v-img>
                    </v-card>
               </v-col>
              <v-col cols="12" sm="6" md="6" > </v-col>
        </v-row>
       
    </div>
</template>


<script>
 export default {
    middleware: 'auth',
    data: () => ({
      
    }),
  }
</script>