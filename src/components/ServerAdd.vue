<template>
  <Form inline>
    <FormItem>
      <Input type="text" v-model="formInline.user" placeholder="Username">
      <Icon type="ios-person-outline" slot="prepend"/>
      </Input>
    </FormItem>
    <FormItem prop="password">
      <Input type="password" v-model="formInline.password" placeholder="Password">
      <Icon type="ios-locked-outline" slot="prepend"/>
      </Input>
    </FormItem>
    <FormItem>
      <Button type="primary" @click="handleSubmit('formInline')">Signin</Button>
    </FormItem>
  </Form>
</template>

<script>
  import {validationMixin} from 'vuelidate'
  import {Input} from 'vuelidate/lib/validators'
  import * as config from '../util/config'

  export default {
    name: 'ServerAdd',
    mixins: [validationMixin],
    data () {
      return {
        formInline: {
          user: '',
          password: ''
        },
        ruleInline: {
          user: [
            { required: true, message: 'Please fill in the user name', trigger: 'blur' }
          ],
          password: [
            { required: true, message: 'Please fill in the password.', trigger: 'blur' },
            { type: 'string', min: 6, message: 'The password length cannot be less than 6 bits', trigger: 'blur' }
          ]
        }
      }
    },

    methods: {handleSubmit(name) {
        this.$refs[name].validate((valid) => {
          if (valid) {
            this.$Message.success('Success!');
          } else {
            this.$Message.error('Fail!');
          }
        })
      },
      saveUser() {
        console.log(this.form);

        this.$http.post(config.API_URL + '/servers', this.form, {emulateJSON: true}).then(response => {

          console.log(response.data);
          clearForm()
          // get body data
          // this.someData = response.body;

        }, response => {
          console.log("error");
        });
        // clearForm();
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>
