<template>
  <div>
    <form novalidate class="md-layout md-gutter" @submit.prevent="saveUser">

      <div class="md-layout-item">
        <md-field>
          <label for="alias">规则名称</label>
          <md-input name="alias" id="alias" v-model="form.alias"/>
        </md-field>
      </div>
      <div class="md-layout-item">
        <md-field>
          <label for="localPort">本地端口</label>
          <md-input name="localPort" id="localPort" v-model="form.localPort"/>
        </md-field>
      </div>
      <div class="md-layout-item">
        <md-field>
          <label for="remoteHost">远端主机</label>
          <md-input name="remoteHost" id="remoteHost" v-model="form.remoteHost"/>
        </md-field>
      </div>
      <div class="md-layout-item">
        <md-field>
          <label for="remotePort">远端端口</label>
          <md-input name="remotePort" id="remotePort" v-model="form.remotePort"/>
        </md-field>
      </div>
      <div class="md-layout-item">
        <md-button type="submit" class="md-raised md-primary">创建规则</md-button>
      </div>
    </form>
  </div>
</template>

<script>
  import {validationMixin} from 'vuelidate'
  import {email, maxLength, minLength, required} from 'vuelidate/lib/validators'

  export default {
    name: 'ServerAdd',
    mixins: [validationMixin],
    data: () => ({
      form: {
        alias: null,
        localPort: null,
        remotePort: null,
        remoteHost: null
      }
    }),

    methods: {

      clearForm() {
        this.$v.$reset()
        this.form.alias = null
        this.form.localPort = null
        this.form.remotePort = null
        this.form.remoteHost = null
      },
      saveUser() {
        console.log(this.form);
        this.$http.post('http://localhost:1049/servers',this.form,{emulateJSON: true}).then(response => {
          console.log(response.data);
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
