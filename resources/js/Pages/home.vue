<template>
    <v-app>
        <v-main>
            <div class="d-flex justify-center">
                <v-card elevation="2" width="400" height="320" class="mt-15 rounded-shaped b">
                    <div class="text-center mt-3">
                        <span> LOGIN </span>
                    </div>
                    <div v-if="$page.props.flash.message" class="alert">
                        {{ $page.props.flash.message }}
                    </div>
                    <v-card-text>
                        <v-form color="white">
                            <v-text-field label="Username" v-model="form.username"
                                :error-messages="errors.username"></v-text-field>
                            <v-text-field label="Password" type="password" v-model="form.password"
                                :error-messages="errors.password"></v-text-field>
                            <v-btn block color="primary" @click="login">Login</v-btn>
                            <div class="mt-5">
                                <v-btn elevation="2" small x-small @click="register">Register</v-btn>
                            </div>
                        </v-form>
                    </v-card-text>
                </v-card>
            </div>
            div
        </v-main>
    </v-app>
</template>

<script>
import { router } from '@inertiajs/vue3'
export default {
    props: {
        errors: Object,
    },
    data() {
        return {
            form: {
                username: "",
                password: "",
            }
        }
    },
    methods: {
        login() {
            router.post('/login', this.form)
        },
        register() {
            router.get('/register')
        }
    },
};

</script>

