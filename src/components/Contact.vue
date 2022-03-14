<template>
    <v-container id="contact">
        <h3>Kontakt</h3>
        <validation-observer
            ref="observer"
            v-slot="{ invalid }"
        >
            <form enctype=multipart/form-data>
                <!-- <input type="hidden" name="_captcha" value="false">
                <input type="hidden" name="_next" value="http://localhost:8085/"> -->
                <!-- formsubmit.co -->
                <validation-provider
                    v-slot="{ errors }"
                    name="name"
                    rules="required|max:10"
                >
                    <v-text-field
                        v-model="name"
                        :counter="10"
                        :error-messages="errors"
                        label="Namn"
                        required
                        name="namn"
                    ></v-text-field>
                </validation-provider>

                <validation-provider
                    v-slot="{ errors }"
                    name="email"
                    rules="required|email"
                >
                    <v-text-field
                        v-model="email"
                        :error-messages="errors"
                        label="E-mail"
                        required
                        name="email"
                    ></v-text-field>
                </validation-provider>

                <validation-provider
                    v-slot="{ errors }"
                    name="message"
                    rules="required"
                >
                    <v-textarea
                        v-model="message"
                        :error-messages="errors"
                        data-vv-name="description"
                        name="message"
                        label="Ställ din fråga här!"
                        value=""
                        hint="Tex. en bokningsförfråga"
                        required
                    ></v-textarea>
                </validation-provider>

                <validation-provider
                    v-slot="{ errors }"
                    name="attachment"
                >
                    <v-file-input
                        v-model="file"
                        :error-messages="errors"
                        name="attachment"
                        accept="image/*"
                        label="Bifoga fil"
                        clearable
                    ></v-file-input>
                </validation-provider> 

                <v-btn
                    class="mr-4"
                    type="submit"
                    :disabled="invalid"
                     @click.prevent="submit"
                >
                    skicka
                </v-btn>
                <v-btn @click="clear">
                    rensa
                </v-btn>
            </form>
        </validation-observer>
        <v-snackbar
            v-model="snackbar"
            >
            {{ text }}

            <template v-slot:action="{ attrs }">
                <v-btn
                color="pink"
                text
                v-bind="attrs"
                @click="snackbar = false"
                >
                Stäng
                </v-btn>
            </template>
        </v-snackbar>
    </v-container>
</template>

<script>
import axios from 'axios'
import { required, email, max, regex } from 'vee-validate/dist/rules'
import { extend, ValidationObserver, ValidationProvider, setInteractionMode } from 'vee-validate'

  setInteractionMode('eager')

  extend('required', {
    ...required,
    message: '{_field_} can not be empty',
  })

  extend('max', {
    ...max,
    message: '{_field_} may not be greater than {length} characters',
  })

  extend('regex', {
    ...regex,
    message: '{_field_} {_value_} does not match {regex}',
  })

  extend('email', {
    ...email,
    message: 'Email must be valid',
  })
export default {
    name: 'contact',
    components: {
      ValidationProvider,
      ValidationObserver,
    },
    data() {
        return {
            name: '',
            email: '',
            message: '',
            file: null,
            snackbar: false,
            text: `Meddelandet är skickat!`,
        }
    },
    methods: {
        submit () {
            this.$refs.observer.validate()
            axios.defaults.headers.post['Content-Type'] = 'application/json';
            axios.post('https://formsubmit.co/ajax/info@evvab.se', {
                name: this.name,
                email: this.email,
                message: this.message,
                file: this.file
            })
            .then((response) => {
                console.log(response)
                if(response.status === 200){
                    this.clear()
                    this.snackbar = true
                }
            })
            .catch(error => console.log(error));
        },
        clear () {
            this.name = ''
            this.email = ''
            this.message = ''
            this.file = null
            this.$refs.observer.reset()
        },
    },
}
</script>

<style scoped>
a {
    text-decoration: none;
    color: black !important;
    cursor: pointer;
}
</style>