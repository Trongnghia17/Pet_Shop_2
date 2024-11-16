<template>
  <v-container class="register-container" fluid>
    <v-row justify="center" align="center">
      <v-col cols="12" sm="8" md="4">
        <v-card outlined>
          <v-card-title class="headline text-center">Đăng ký</v-card-title>
          <v-card-text>
            <v-form @submit.prevent="register" ref="form">
              <v-text-field
                  v-model="name"
                  label="Họ và tên"
                  required
                  outlined
              ></v-text-field>
              <v-text-field
                  v-model="email"
                  label="Email"
                  type="email"
                  required
                  outlined
              ></v-text-field>
              <v-text-field
                  v-model="password"
                  label="Mật khẩu"
                  type="password"
                  required
                  outlined
              ></v-text-field>
              <v-text-field
                  v-model="confirmPassword"
                  label="Xác nhận mật khẩu"
                  type="password"
                  required
                  outlined
              ></v-text-field>
              <v-btn type="submit" color="success" block>Đăng ký</v-btn>
            </v-form>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <router-link to="/login">
              <v-btn text>Đã có tài khoản? Đăng nhập</v-btn>
            </router-link>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'RegisterPage',
  data() {
    return {
      name: '',
      email: '',
      password: '',
      confirmPassword: '',
    };
  },
  methods: {
    register() {
      if (this.password !== this.confirmPassword) {
        alert('Mật khẩu xác nhận không khớp!');
        return;
      }
      console.log(`Đăng ký thành công: ${this.email}`);
      alert('Đăng ký thành công!');
    },
  },
};
</script>

<style>
.register-container {
  height: 100vh;
  display: flex;
  align-items: center;
  background-color: #f5f5f5;
}
</style>
