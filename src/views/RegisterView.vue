<template>
  <div class="container">
    <img class="wave" src="../assets/img/wave.png">
	<div class="container">
		<div class="img">
			<img src="../assets/img/undraw_window_shopping_re_0kbm.svg">
		</div>
		<div class="login-content" id="form-1">
			<form action="index.html">
				<img src="../assets/img/avatar.svg">
				<h2 class="title">Let's Register</h2>
				<!-- <div class="input-div one">
					<div class="i">
						<font-awesome-icon :icon="['fas', 'user']" />
					</div>
					<div class="div">
						<h5>Username</h5>
						<input type="text" class="input">
					</div>
				</div>
				<div class="input-div pass">
					<div class="i">
						<font-awesome-icon :icon="['fas', 'lock']" />
					</div>
					<div class="div">
						<h5>Password</h5>
						<input type="password" class="input">
					</div>
				</div>
				<div class="input-div phone">
					<div class="i">
						<i class="fas fa-phone"></i>
					</div>
					<div class="div">
						<h5>Phone Number</h5>
						<input type="text" class="input">
					</div>
				</div>
				<div class="input-div phone">
					<div class="i">
						<i class="fas fa-envelope"></i>
					</div>
					<div class="div">
						<h5>Email</h5>
						<input type="email" class="input">
					</div>
				</div>
				<div class="input-div code">
					<div class="i">
						<i class="fas fa-shield-alt"></i>
					</div>
					<div class="div">
						<h5>First Name</h5>
						<input type="text" class="input ">
					</div>
				</div> -->
        <div class="input-div one">
					<div class="i">
						<i class="fas fa-user"></i>
					</div>
					<div class="div">
						<h5>First Name</h5>
						<input id="fname" type="text" class="input">
						<small></small>
					</div>
				</div>
				<div class="input-div one">
					<div class="i">
						<i class="fas fa-user"></i>
					</div>
					<div class="div">
						<h5>Last Name</h5>
						<input id="lname" type="text" class="input">
						<small></small>
					</div>
				</div>
				<div class="input-div pass">
					<div class="i">
						<i class="fas fa-lock"></i>
					</div>
					<div class="div">
						<h5>Password</h5>
						<input id="pass" type="password" class="input">
						<small></small>
					</div>
				</div>
				<div class="input-div pass">
					<div class="i">
						<i class="fas fa-lock"></i>
					</div>
					<div class="div">
						<h5>Password Confirm</h5>
						<input id="conpass" type="password" class="input">
						<small></small>
					</div>
				</div>
				<div class="input-div phone">
					<div class="i">
						<i class="fas fa-phone"></i>
					</div>
					<div class="div">
						<h5>Phone Number</h5>
						<input id="phone" type="text" class="input">
						<small></small>
					</div>
				</div>
				<div class="input-div phone">
					<div class="i">
						<i class="fas fa-envelope"></i>
					</div>
					<div class="div">
						<h5>Email</h5>
						<input id ="emails" type="email" class="input">
						<small></small>
					</div>
				</div>
				<input type="submit" class="btn" value="Register">
			</form>
		</div>
	</div>

  <!-- <img class="wave" src="img/wave.png">
	<div class="container">
		<div class="img">
			<img src="img/undraw_shopping_re_hdd9.svg">
		</div>
		<div class="login-content" id="form-1">
			<form action="index.html">
				<img src="img/undraw_personal_info_re_ur1n.svg">
				<h2 class="title">Let's Register</h2>
				<div class="input-div one">
					<div class="i">
						<i class="fas fa-user"></i>
					</div>
					<div class="div">
						<h5>First Name</h5>
						<input id="fname" type="text" class="input">
						<small></small>
					</div>
				</div>
				<div class="input-div one">
					<div class="i">
						<i class="fas fa-user"></i>
					</div>
					<div class="div">
						<h5>Last Name</h5>
						<input id="lname" type="text" class="input">
						<small></small>
					</div>
				</div>
				<div class="input-div pass">
					<div class="i">
						<i class="fas fa-lock"></i>
					</div>
					<div class="div">
						<h5>Password</h5>
						<input id="pass" type="password" class="input">
						<small></small>
					</div>
				</div>
				<div class="input-div pass">
					<div class="i">
						<i class="fas fa-lock"></i>
					</div>
					<div class="div">
						<h5>Password Confirm</h5>
						<input id="conpass" type="password" class="input">
						<small></small>
					</div>
				</div>
				<div class="input-div phone">
					<div class="i">
						<i class="fas fa-phone"></i>
					</div>
					<div class="div">
						<h5>Phone Number</h5>
						<input id="phone" type="text" class="input">
						<small></small>
					</div>
				</div>
				<div class="input-div phone">
					<div class="i">
						<i class="fas fa-envelope"></i>
					</div>
					<div class="div">
						<h5>Email</h5>
						<input id ="emails" type="email" class="input">
						<small></small>
					</div>
				</div>


				<input type="submit" class="btn" value="Register">
			</form>
		</div>
	</div> -->
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      isLogin: true,
      username: "",
      password: "",
      token: "",
      user: {},
    };
  },
  methods: {
    async login() {
      const response = await axios.post("http://localhost:8081/api/login", {
        username: this.username,
        password: this.password,
      });
      this.token = response.data.jwt;
      localStorage.setItem("token", this.token);
      window.location.replace("http://localhost:8080/");
    },
    // async current() {
    //   try {
    //     const response = await axios.get("http://localhost:8081/api/current", {
    //       headers:{
    //         'Access-Control-Allow-Origin': '*',
    //         'Authorization': 'Bearer ' + localStorage.getItem('token'),
    //       },
    //     });
    //     this.user = response.data.userEntity;
    //     this.$emit('message-sent', this.user);
    //     console.log(this.user);
    //   } catch (error) {
    //     console.error(error);
    //   }
    // },
    // async getRandom() {
    //   try {
    //     const response = await axios.get("http://localhost:8081/api/random", {
    //       headers: {
    //         Authorization: "Bearer " + localStorage.getItem("token"),
    //       },
    //     });
    //     console.log(response);
    //   } catch (error) {
    //     console.error(error);
    //   }
    // },
    // sendMessage() {
    //   this.$emit('message-sent', 'Hello from child');
    // }
  },
};
</script>

<style scoped>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  font-family: "Poppins", sans-serif;
  overflow: hidden;
}

.wave {
  position: fixed;
  bottom: 0;
  left: 0;
  height: 100%;
  z-index: -1;
}

.container {
  width: 100vw;
  height: 100vh;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 7rem;
  padding: 0 2rem;
}

.img {
  display: flex;
  justify-content: flex-end;
  align-items: center;
}

.login-content {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  text-align: center;
}

.img img {
  width: 500px;
}

form {
  width: 360px;
}

.login-content img {
  height: 100px;
}

.login-content h2 {
  margin: 15px 0;
  color: #333;
  text-transform: uppercase;
  font-size: 2.9rem;
}

.login-content .input-div {
  position: relative;
  display: grid;
  grid-template-columns: 7% 93%;
  margin: 25px 0;
  padding: 5px 0;
  border-bottom: 2px solid #d9d9d9;
}

.login-content .input-div.one {
  margin-top: 0;
}

.i {
  color: #d9d9d9;
  display: flex;
  justify-content: center;
  align-items: center;
}

.i i {
  transition: 0.3s;
}

.input-div > div {
  position: relative;
  height: 45px;
}

.input-div > div > h5 {
  position: absolute;
  left: 10px;
  top: 50%;
  transform: translateY(-50%);
  color: #999;
  font-size: 18px;
  transition: 0.3s;
}

.input-div:before,
.input-div:after {
  content: "";
  position: absolute;
  bottom: -2px;
  width: 0%;
  height: 2px;
  background-color: #38d39f;
  transition: 0.4s;
}

.input-div:before {
  right: 50%;
}

.input-div:after {
  left: 50%;
}

.input-div.focus:before,
.input-div.focus:after {
  width: 50%;
}

.input-div.focus > div > h5 {
  top: -5px;
  font-size: 15px;
}

.input-div.focus > .i > i {
  color: #38d39f;
}

.input-div > div > input {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  border: none;
  outline: none;
  background: none;
  padding: 0.5rem 0.7rem;
  font-size: 1.2rem;
  color: #555;
  font-family: "poppins", sans-serif;
}

.input-div.pass {
  margin-bottom: 4px;
}

a {
  display: block;
  text-align: right;
  text-decoration: none;
  color: #999;
  font-size: 0.9rem;
  transition: 0.3s;
}

a:hover {
  color: #38d39f;
}

.btn {
  display: block;
  width: 100%;
  height: 50px;
  border-radius: 25px;
  outline: none;
  border: none;
  background-image: linear-gradient(to right, #32be8f, #38d39f, #32be8f);
  background-size: 200%;
  font-size: 1.2rem;
  color: #fff;
  font-family: "Poppins", sans-serif;
  text-transform: uppercase;
  margin: 1rem 0;
  cursor: pointer;
  transition: 0.5s;
}
.btn:hover {
  background-position: right;
}

@media screen and (max-width: 1050px) {
  .container {
    grid-gap: 5rem;
  }
}

@media screen and (max-width: 1000px) {
  form {
    width: 290px;
  }

  .login-content h2 {
    font-size: 2.4rem;
    margin: 8px 0;
  }

  .img img {
    width: 400px;
  }
}

@media screen and (max-width: 900px) {
  .container {
    grid-template-columns: 1fr;
  }

  .img {
    display: none;
  }

  .wave {
    display: none;
  }

  .login-content {
    justify-content: center;
  }
}
</style>

