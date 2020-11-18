<template>
    <v-row  >
         <v-col cols="12" sm="6" md="4" > </v-col>
         <v-col cols="12" sm="6" md="4" > 
               <v-card class="mx-auto pa-md-4 pa-4" outlined>
                    <v-list-item-title class="headline mb-1 gray">
                    New Account 
                    </v-list-item-title>


                    <v-list-item-title class="sub-headline mb-1 gray">
                    <p>
                        Already Registered
                        <router-link :to="{ name: 'auth-login'}"  >Login</router-link>
                    </p>
                    </v-list-item-title>
                    <v-divider></v-divider>
                    <div class="mt-5">
                    <v-form  ref="form" v-model="valid" lazy-validation @submit.prevent="register">
                        <v-text-field
                            v-model="form.name"
                            :rules="nameRules"
                            label="Name"
                            outlined
                            clearable
                            required
                            ></v-text-field>
                        <v-text-field
                            v-model="form.email"
                            :rules="emailRules"
                            label="Email"
                            outlined
                            clearable
                            required
                            ></v-text-field>
                        <v-text-field
                            v-model="form.password"
                            :rules="passwordRules"
                            label="Password"
                            outlined
                            clearable
                            required
                            ></v-text-field>
                         <v-checkbox
                            v-model="checkbox"
                            :rules="[v => !!v || 'You must agree to continue!']"
                            label="Do you agree?"
                            required
                            ></v-checkbox>
                        <v-btn
                            :disabled="!valid"
                            color="primary"
                            class="mr-4"
                            type="submit" 
                            value="Login"
                            block large
                            @click="validate"
                            >
                            Register
                        </v-btn>
                    </v-form>
                    </div>
                </v-card>
         </v-col>
         <v-col cols="12" sm="6" md="4" > </v-col>
    </v-row>
</template>

<script>

export default {
    components: {
    },
    data() {
        return {
             valid: true,
             nameRules: 'name',
            form: {
                name: '',
                email: '',
                password: ''
            },
            nameRules: [
                v => !!v || 'Name is required',
            ],
            passwordRules: [
                v => !!v || 'Password is required',
            ],
            emailRules: [
                v => !!v || 'E-mail is required',
                v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
            ],
            checkbox: false,
            error: this.$route.query.error
        }
    },
    methods: {
         validate () {
         this.$refs.form.validate()
       },
        async register() {
            try {
                await this.$axios.post('api/auth/register', this.form);
            } catch(e) {
                return;
            }
            this.$auth.login({data: this.form});
            
            this.$router.push({name: 'index'});
        }
    }
}
</script>
