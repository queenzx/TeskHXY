<template>
  <div class="login">
    <h2>千库网智慧数据登录</h2>
    <div class="login_form">
      <h3>用户登录</h3>
      <form ref="ruleForm" :model="ruleForm" :rules="rules">
		<p class="p">
			<input type="text" placeholder="请输入用户名">
		</p>
		<p class="p">
			<input type="password" placeholder="请输入密码">
		</p>
		<p class="pp">
			<input type="checkbox" name="rememberNumber" checked>
			<span class="sp">记住账号</span>
			<span type="text">忘记密码</span>
		</p>
		<p><button click="submitForm('ruleForm')">登录</button></p>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    let validateName = (rule, value, callback) => {
      if (value === "") {
        callback(new Error("请输入用户名"));
      } else {
        callback();
      }
    };

    let validatePass = (rule, value, callback) => {
      if (value === "") {
        callback(new Error("请输入密码"));
      } else {
        callback();
      }
    };

    return {
      name: "login",
      ruleForm: {
        username: "",
        password: "",
        rememberNumber: false,
      },
      rules: {
        username: [
          {
            validator: validateName,
            trigger: "blur",
          },
        ],
        password: [
          {
            validator: validatePass,
            trigger: "blur",
          },
        ],
      },
      redirect: undefined,
    };
  },
  methods: {},
};
</script>

<style scoped>
.login {
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  flex-direction: column;
  background: #0C1D91;
  color: white;
  overflow:hidden;
}
.login h2{
	margin-top:160px;
	position: relative;
}


.login .login_form{
	margin: 50px auto;
	width: 500px;
	padding-top:20px;
	height:100%;
	border: rgba(4, 172, 247,0.3) 2px solid;
	background: linear-gradient(blue, blue) left top,
		linear-gradient(blue, blue) left top,
		linear-gradient(blue, blue) right top,
		linear-gradient(blue, blue) right top,
		linear-gradient(blue, blue) left bottom,
		linear-gradient(blue, blue) left bottom,
		linear-gradient(blue, blue) right bottom,
		linear-gradient(blue, blue) right bottom;
	background-repeat: no-repeat;
	background-color:rgba(49,113,192, 0.3) ;
	background-size: 1px 24px, 24px 1px;
}
.login .login_form  h3 {
	font-size: 20px;
	font-weight: normal;
	margin-bottom: 20px;
	text-align: center;
}
.login .login_form  p {
	margin:10px;
}
.login .login_form  .p input {
	width:50%;
	height:30px;
	border: #3979C1 1px solid;
	border-radius:3px;
	outline: none;
	background: none;
	margin:5px;
	color:white;
}
.login .login_form  .p input::-webkit-input-placeholder {
	color:white;
	padding-left:5px;
	font-size:13px;
}
.login .login_form  .p input:-moz-placeholder {
	color:white;
	padding-left:5px;
}
.login .login_form  .p input:-moz-placeholder-placeholder {
	color:white;
	padding-left:5px;
}
.login .login_form  .p input:-ms-input-placeholder {
	color:white;
	padding-left:5px;
}
.login .login_form .pp input{
	float:left;
	margin-left: 120px;
}
.login .login_form .pp .sp{
	float:left;
	margin-left: 5px;
}

.login .login_form p button{
	width:50%;
	height:30px;
	outline: none;
	border:none;
	border-radius:3px;
	background: #64A7E3;
	color:white;
	margin-top:10px;
}
</style>