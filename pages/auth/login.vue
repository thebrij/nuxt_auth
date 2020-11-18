<template>
    <div>
        <!-- start  -->
            <v-row  >
            <v-col cols="12" sm="6" md="4" > </v-col>
            <v-col cols="12" sm="6" md="4" >
                <v-card class="mx-auto pa-md-4 pa-4" outlined>
                    <v-list-item-title class="headline mb-1 gray">
                    Login 
                    </v-list-item-title>


                    <v-list-item-title class="sub-headline mb-1 gray">
                    <p>
                        Doesn't have an account? 
                        <router-link :to="{ name: 'auth-register'}"  >Sign In</router-link>
                    </p>
                    </v-list-item-title>
                    <v-divider></v-divider>
                    <div class="mt-5">
                    <v-form  ref="form" v-model="valid" lazy-validation @submit.prevent="login">
                        <v-text-field
                            v-model="form.email"
                            v-on:input="resetValidation"
                            :rules="emailRules"
                            label="Email"
                            outlined
                            clearable
                            required
                            :error="errors" 
                             :error-messages="errorMessages"
                        ></v-text-field>
                       
                        <v-text-field
                            v-model="form.password"
                            v-on:input="resetValidation"
                            :rules="passwordRules"
                            label="Password"
                            outlined
                            clearable
                            required
                            
                        ></v-text-field>

                        <router-link :to="{ name: 'auth-register'}">
                            <p>Fotget your password?</p>
                        </router-link>

                        <v-btn
                            :disabled="!valid"
                            color="primary"
                            class="mr-4"
                            type="submit" 
                            value="Login"
                            block large
                            @click="validate"
                            >
                            Login
                        </v-btn>

                        
                    </v-form>
                    </div>
                </v-card>
            </v-col>
            <v-col cols="12" sm="6" md="4" >
               
             </v-col>
        </v-row>
        <!-- end -->
    </div>
</template>

<script>
export default {
    data() {
        return {
            form: {
                email: '',
                password: ''
            },
            
            valid: true,
            errors: false,
            errorMessages:'',
            passwordRules: [
                v => !!v || 'Password is required',
            ],
            emailRules: [
                v => !!v || 'E-mail is required',
                v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
            ],
           
        }
    },
    
    methods: {
        validate () {
         this.$refs.form.validate()
        },
        
        resetValidation () {
            this.$refs.form.resetValidation()
        },
       
        async login() {
            await this.$auth.login({
                data: this.form
            })
            .catch(errors => {
                // console.error(errors.response.data.errors.email)
                this.errors = true
                this.valid  = true
                this.errorMessages = errors.response.data.errors.email
            });
            this.$router.push({
                path: '/dashboard'
            });
        }
    }
}
</script>

<style>
.top {
    margin-top: 80px;
}
</style>