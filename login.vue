<template>
    <div class="wrapper">
        <div class="center">
            <div class="login-bg">
                <image :style="imageStyle" src="./resources/img/login_bg.png" />

                <div class="login">
                    <div class="input-wrapper">
                        <image class="title-image" src="./resources/img/logo_login.png" />
                    </div>
                    <div class="input-wrapper">
                        <text class="input-title-text">登录</text>
                    </div>
                    <div class="input-wrapper">
                        <input onchange="onchangeUserNumber" class="input" type="text" placeholder="用户名、手机号或邮箱" autofocus="true" value="" />
                        <!-- <image class="input-img" src="./resources/img/login_input_user_img.png" /> -->
                    </div>
                    <div class="line">
                        <div style="width:500px;height:2px;background-color:#FFF">
                        </div>
                    </div>

                    <div class="input-wrapper">
                        <input onchange="onchangeUserPassword" class="input" type="password" placeholder="密码(至少8位)" value="" />
                        <!-- <image class="input-img" src="./resources/img/login_input_pass_img.png" /> -->
                    </div>
                    <div class="line">
                        <div style="width:500px;height:2px;background-color:#FFF">
                        </div>
                    </div>

                    <div class="remPassword">

                        
                    </div>

                    <div class="input-wrapper">
                        <div class="input-login" onclick="login">
                            <text class="input-login-text">登录</text>
                        </div>
                        <div class="input-register" onclick="register">
                            <text class="input-register-text">注册</text>
                        </div>
                    </div>
                    <!-- <div class="input-wrapper">
                        <text class="input-forget" onclick="findPassword">找回密码</text>
                        <text class="input-register" onclick="register">立即注册</text>
                    </div> -->
                </div>
            </div>
        </div>
    </div>
</template>
<script>
const modal = weex.requireModule("modal");
module.exports = {
    data() {
        return {
            userNumber: "",
            userPassword: "",
            imageStyle: {
                position: "absolute",
                width: "750px",
                height:
                    weex.config.env.deviceHeight *
                        750 /
                        weex.config.env.deviceWidth +
                    "px"
            }
        };
    },
    methods: {
        onchangeUserNumber: function(event) {
            this.userNumber = event.value;
        },
        onchangeUserPassword: function(event) {
            this.userPassword = event.value;
        },
        //找回密码
        fingPassword: function() {
            modal.toast({
                message: "Hello，找回密码暂时未开发，后续我们会进行完善。"
            });
        },
        //注册
        register: function() {
            modal.toast({
                message: "Hello，注册暂时未开发，后续我会进行完善。"
            });
        },
        //处理登录
        login: function() {
            if (this.userNumber.length < 1) {
                modal.toast({ message: "请输入手机号。" });
                return;
            } else if (this.userPassword.length < 1) {
                modal.toast({ message: "请输入密码" });
                return;
            }

            modal.toast({ message: "登录成功" });
        }
    }
};
</script>
<style scoped >
.wrapper {
    /* background-color: aqua; */
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
}
.center {
    justify-content: center;
    align-items: center;
}
.login-bg {
    flex: 1;
}
.title-image {
    width: 150px;
    height: 150px;
    margin-left: 36%;
}
.input-title-text {
    height: 80px;
    width: 550px;
    text-align: center;
    color: #fff;
    font-size: 45px;
}

.line {
    margin-left: 120px;
}

.login {
    margin-top: 180px;
}
.input-wrapper {
    width: 550px;
    margin-left: 100px;
    margin-right: 100px;
    margin-bottom: 30px;
}
.input {
    font-size: 35px;
    height: 80x;
    width: 550px;
    padding-left: 90px;
    padding-top: 50px;
    margin-bottom: 15px;
    background-color: rgba(0, 0, 0, 0);
    outline: none;
    placeholder-color: #ffffff;
}
.input-img {
    position: absolute;
    top: 10px;
    left: 15px;
    width: 50px;
    height: 50px;
}
.input-login {
    height: 100px;
    width: 550px;
    background-color: #fff;
    border-radius: 50px;
    margin-top: 40px;
}
.input-login-text {
    height: 80px;
    width: 550px;
    text-align: center;
    margin-top: 10px;
    line-height: 80px;
    color: rgb(35, 154, 233);
    font-size: 35px;
}
.input-register {
    height: 100px;
    width: 550px;
    background-color: rgba(35, 154, 233, 0);
    border-radius: 50px;
    margin-top: 40px;
    border: 2px solid #fff;
}
.input-register-text {
    height: 80px;
    width: 550px;
    text-align: center;
    margin-top: 10px;
    line-height: 80px;
    color: #fff;
    font-size: 35px;
}
.input-forget {
    position: absolute;
    left: 30px;
    font-size: 30px;
}
</style>
