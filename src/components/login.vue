<template>
  <div>
    <h1>Login</h1>
    <div v-if="!isLogin">
      <form>
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="email" />
        </div>
        <div>
          <label for="password">Password:</label>
          <input type="password" id="password" v-model="password" />
        </div>
        <div>
          <label for="confirmPassword">Confirm Password:</label>
          <input
              type="password"
              id="confirmPassword"
              v-model="confirmPassword"
          />
        </div>
        <div>
          <button @click.prevent="signUp">Sign Up</button>
          <button @click.prevent="togglePage">Login</button>
        </div>
      </form>

    </div>
    <div v-else>
      <form>
        <!--        邮箱-->
        <div>
          <div class="left-text">Email</div>
          <div>
            <el-input v-model="input" placeholder="Please input" />
          </div>
        </div>
        <!--        密码-->
        <div>
          <div class="left-text">Password</div>
          <div>
            <el-input
                v-model="input"
                type="password"
                placeholder="Please input password"
                show-password
            />
          </div>
        </div>
        <!--        login-button-->
        <div>
          <button></button>
        </div>
        <div>
          <span>还没有账号？</span>
          <span>创建一个新的账号</span>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "login",
  data() {
    return {
      email: '',
      password: '',
      confirmPassword: '',
      isLogin: false,
    };
  },
  methods: {
    togglePage() {
      this.isLogin = !this.isLogin;
    },
    login() {
      // Your login logic here
      console.log(`Login with email: ${this.email} and password: ${this.password}`);
    },
    signUp() {
      // Your sign-up logic here
      console.log(`Sign up with email: ${this.email}, password: ${this.password} and confirm password: ${this.confirmPassword}`);
    },
  },
}
</script>

<style scoped>
.left-text{
  font-size: 1.2em;
  text-align: left;
}
</style>
