<template>
  <div>
    <div style="display: flex;justify-content: center;margin-top: 150px">
      <el-card style="width:400px">
        <div slot="header" class="clearfix">
          <span>登录</span>
        </div>
        <table>
          <tr>
            <td>用户名</td>
            <td style="width: 70%" >
               <el-input v-model="user.name" placeholder="请输入用户名/手机号/邮箱"></el-input>
            </td>
          </tr>
           <tr>
            <td>密码</td>
            <td colspan="2" >
             <el-input type="password" v-model="user.password" placeholder="请输入密码"></el-input>
            </td>
          </tr>
          <tr>
            <td colspan="2">
              <el-button type="primary" style="width:350px" @click="login">登录</el-button>
            </td>
          </tr>

        </table>
      </el-card>
    </div>
  </div>
</template>
<script>
export default {
  name: "Login",
  data() {
    return {
      user: {
        username: "",
        password: ""
      }
    };
  },
  methods: {
    login:function(){
      alert(this.user.name)
      alert(this.user.password)
    }
  }
};
</script>