<template>
  <div class="content">
    <!-- header -->
    <div class="header">
      <div>
        <img class="header_img" src="../assets/header.png" alt="">
      </div>
      <div class="login_register">
        <div class="login" @click="handleClickLogin">登录</div>
        <div class="register" @click="handleClickRegister">注册</div>
      </div>     
    </div>

    <!-- title -->
    <div class="title">
      <div>
        <div class="title_left" style="position: relative;z-index: 1;">
        <img class="header_img" style="opacity: 0.8;" src="../assets/header.png">
        <div class="title_text">
          <div style="font-weight: 1000;font-family: Helvetica;letter-spacing: -1.44px;">
            Markhand
          </div>
          <div style="font-size:50px;font-weight:600;">
            一键标注
          </div>
          </div>
        </div>
        <div class="download_area">
          <div class="downLoad">
            下载sketch插件
          </div>
          <div style="display:flex;height:40px;align-items:center;">
            <div>
              查看示例
            </div>
            <div style="background-color: #04DDA3;border-radius:40px;margin-left:20px;">
              <svg style="font-size:40px" class="icon" aria-hidden="true">
                <use  xlink:href="#icon-xiangyousanjiaoxing-copy"></use>
              </svg>
            </div>
          </div>
        </div>
      </div>
      
      <div class="video">
        <video-player class="video-player vjs-custom-skin" 
              ref="videoPlayer" 
              :playsinline="true" 
              :options="playerOptions">
        </video-player> 
      </div>
    </div>

    <!-- main -->
    <div class="main">
      <!-- 左右布局 -->
      <div class="main_item">
        <div class="main_left">
          <div class="main_leftText">
            <div style="font-size:50px;font-weight:bold;">
            一键导出HTML
            </div>
            <div style="margin-top:50px;display:flex;align-items:center;font-size:16px;">
              <div style="width:10px;height:10px;border-radius:50%;background-color:#878BAD;" />
              <div style="text-align:left;margin-left:20px;">
                一键自动生成 HTML 页面，离线下检查所有设计细节，包括 CSS 样式。
              </div>
            </div>
            <div style="margin-top:50px;display:flex;align-items:center;font-size:16px;">
              <div style="width:10px;height:10px;border-radius:5px;background-color:#878BAD" />
              <div style="text-align:left;margin-left:20px;">这是文本这是文本这是文本这是文本这是文本这是文本这是文本这是文本。</div>
            </div>
          </div>
          <img class="main_center" style="bottom:0;right:20px;" src="../assets/separate.png" >
        </div>
        <div class="main_right">
          <img style="width:50%;height:50%;position: absolute;top:0;right:0;" src="../assets/bj1.png">
          <img style="width:95%;height:95%;position: absolute;bottom:0;left:0;" src="../assets/main1.png">
        </div>
      </div>
      <div class="main_item">
        <div class="main_right">
          <img style="width:50%;height:50%;position: absolute;bottom:0;left:0;" src="../assets/bj2.png">
          <img style="width:95%;height:95%;position: absolute;top:0;right:0;" src="../assets/main2.png">
        </div>
        <div class="main_right">
          <div class="main_rightText">
            <div style="font-size:50px;font-weight:bold;">
            标注区域&坐标
            </div>
            <div style="margin-top:50px;display:flex;align-items:center;font-size:16px;">
              <div style="width:10px;height:10px;border-radius:5px;background-color:#878BAD;" />
              <div style="text-align:left;margin-left:20px;">
                这是文本这是文本这是文本这是文本这是文本
              </div>
            </div>
            <div style="margin-top:50px;display:flex;align-items:center;font-size:16px;">
              <div style="width:10px;height:10px;border-radius:5px;background-color:#878BAD" />
              <div style="text-align:left;margin-left:20px;">这是文本这是文本这是文本这是文本这是文本这是文本这是文本这是文本</div>
            </div>
          </div>
          <img class="main_center" style="bottom:0;left:20px;" src="../assets/separate.png" >
        </div>
        
      </div>
      <div class="main_item">
        <div class="main_left">
          <div class="main_leftText">
            <div style="font-size:50px;font-weight:bold;">
            标注间隔&尺寸
            </div>
            <div style="margin-top:50px;display:flex;align-items:center;font-size:16px;">
              <div style="width:10px;height:10px;border-radius:5px;background-color:#878BAD;" />
              <div style="text-align:left;margin-left:20px;">
                选中在画板上的一个层或选中任意两个层
              </div>
            </div>
            <div style="margin-top:50px;display:flex;align-items:center;font-size:16px;">
              <div style="width:10px;height:10px;border-radius:5px;background-color:#878BAD" />
              <div style="text-align:left;margin-left:20px;">点击工具栏上的 间隔 按钮或使用快捷键control ⌃ + shift ⇧ + 3 </div>
            </div>
          </div>
          <img class="main_center" style="bottom:0;right:20px;" src="../assets/separate.png" >
        </div>
        <div class="main_right">
          <img style="width:50%;height:50%;position: absolute;top:0;right:0;" src="../assets/bj3.png">
          <img style="width:95%;height:95%;position: absolute;bottom:0;left:0;" src="../assets/main3.png">
        </div>
      </div>
      <div class="main_item">
        <div class="main_right">
          <img style="width:50%;height:50%;position: absolute;bottom:0;left:0;" src="../assets/bj4.png">
          <img style="width:95%;height:95%;position: absolute;top:0;right:0;" src="../assets/main4.png">
        </div>
        <div class="main_right">
          <div class="main_rightText">
            <div style="font-size:50px;font-weight:bold;">
            标注切图
            </div>
            <div style="margin-top:50px;display:flex;align-items:center;font-size:16px;">
              <div style="width:10px;height:10px;border-radius:5px;background-color:#878BAD;" />
              <div style="text-align:left;margin-left:20px;">
                选中在画板上的一个层或选中任意两个层
              </div>
            </div>
            <div style="margin-top:50px;display:flex;align-items:center;font-size:16px;">
              <div style="width:10px;height:10px;border-radius:5px;background-color:#878BAD" />
              <div style="text-align:left;margin-left:20px;">点击工具栏上的 间隔 按钮或使用快捷键control ⌃ + shift ⇧ + 3 </div>
            </div>
          </div>
          <img class="main_center" style="bottom:0;left:20px;" src="../assets/separate.png" >
        </div>
        
      </div>
    </div>
    <div class="download_sketch">下载sketch插件</div>
      <!-- 登录注册弹窗 -->
      <el-dialog
        :visible.sync="login_status"
        width="1000px">
        <div class="dialog_content">
          <div style="width:50%;">
            <img v-if="register_status" style="width:500px;height:500px;" src="../assets/register.png" alt="">
            <img v-else style="width:500px;height:500px;" src="../assets/login.png" alt="">
          </div>
          <div style="font-size:25px;padding-left:30px;text-align:left;padding-top:70px;width:470px">
            {{ register_status?'注册':'登录' }}
            <div style="font-size:15px;margin-top:70px;">
              邮箱
            </div>
            <el-input style="width:500px" placeholder="请输入邮箱" v-model="email"></el-input>
            <div style="font-size:15px;margin-top:30px;">
              密码
            </div>
            <el-input placeholder="请输入密码" show-password v-model="password"></el-input>
            <div class="login_button" style="font-size:10px;margin-top:20px;width: 400px;">
              <div @click="handleClickChange">
                {{ register_status?'已有账号':'忘记密码?' }}
              </div>
              <div class="loginButton">
                {{ register_status?'注册':'登录' }}
              </div>
            </div>
          </div>
          
        </div>
      </el-dialog>
    
  </div>

  
</template>

<script>
export default {
  data() {
    return {
      login_status: false,
      register_status: false,
      email: '',
      password: '',
      playerOptions: {
            playbackRates: [0.5, 1.0, 1.5, 2.0], // 可选的播放速度
            autoplay: false, // 如果为true,浏览器准备好时开始回放。
            muted: false, // 默认情况下将会消除任何音频。
            loop: false, // 是否视频一结束就重新开始。
            preload: 'auto', // 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
            language: 'zh-CN',
            aspectRatio: '16:9', // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
            fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
            sources: [{
              type: "video/mp4", // 类型
              src: require('../assets/video.mp4')// url地址
            }],
            poster: '', // 封面地址
            notSupportedMessage: '此视频暂无法播放，请稍后再试', // 允许覆盖Video.js无法播放媒体源时显示的默认信息。
            controlBar: {
              timeDivider: true, // 当前时间和持续时间的分隔符
              durationDisplay: true, // 显示持续时间
              remainingTimeDisplay: false, // 是否显示剩余时间功能
              fullscreenToggle: true // 是否显示全屏按钮
            }
          }
    }
  },
  methods: {
    handleClickLogin() {
      this.login_status = true
      this.register_status = false
    },
    handleClickRegister() {
      this.login_status = true
      this.register_status = true
    },
    handleClickChange() {
      this.register_status = !this.register_status
    }
  }
}
</script>

<style scoped>
>>>.el-input__inner {
	width: 220px;
  border-radius: 0;
  width: 400px;
  padding-left: 0;
	border-top-width: 0px;
	border-left-width: 0px;
	border-right-width: 0px;
	border-bottom-width: 1px;
}
>>>.el-input__suffix {
  left: 370px;
}
>>>.el-dialog__header {
  display: none;
}
>>>.el-dialog__body {
  height: 500px;
  padding: 0px;
}
.content {
  position: relative;
}
  .icon {
    width: 1em;
    height: 1em;
    vertical-align: -0.15em;
    fill: currentColor;
    overflow: hidden;
  }
  .header {
    display: flex;
    justify-content: space-around;
    align-items: flex-end;
  }
  .header_img {
    width: 512px;
    height: 514px;
    opacity: 0.5;
  }
  .login_register {
    display: flex;
    justify-content: space-around;
    align-items: center;
    font-size: 15px;
    width: 180px;
    height: 40px;
  }
  .login {
    width: 75px;
    height: 40px;
    line-height: 40px;
    border-right: #D8D8D8 2px solid;
  }
  .register {
    width: 75px;
    height: 40px;
    line-height: 40px;
    background-color: #04DDA3;
    border-radius:20px 0 20px 20px;
  }
  .login:hover {
    cursor: pointer;
  }
  .register:hover {
    cursor: pointer;
  }

  .loginButton {
    width: 170px;
    height: 50px;
    font-size: 18px;
    text-align: center;
    line-height: 50px;
    background-color: #04DDA3;
    border-radius:25px 0 25px 25px;
  }


  .title {
    margin-top: 100px;
    display: flex;
    justify-content: flex-start;
  }
  .title_text {
    position: absolute;
    z-index: 2;
    left: 300px;
    top: 0;
    font-size:70px;
    color:#151D31;
    text-align: left;
  }
  .download_area {
    position: absolute;
    width: 800px;
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    font-size: 15px;
  }
  .downLoad {
    width: 174px;
    height: 50px;
    color: #000000;
    font-family: PingFangSC-Regular;
    letter-spacing: -0.63px;
    line-height: 50px;
    background-color: #04DDA3;
    border-radius:20px 0 20px 20px;
    margin-left: 300px;
  }
  .video {
    margin-left: 500px;
    width: 800px;
    height: 600px;
  }

  .main {
    width: 80%;
    margin: 100px auto;
  }
  .main_item {
    margin-top: 100px;
    display: flex;
    height: 580px;
    justify-content: space-around;
  }
  .main_left {
    position: relative;
    width: 50%;
    display: flex;
    justify-content: flex-start;
  }
  .main_right {
    position: relative;
    width: 50%;
    display: flex;
    justify-content: flex-end;
  }
  .main_leftText {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: left;
    width:400px;
    height: 400px;
  }
  .main_rightText {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: right;
    width:400px;
    height: 400px;
  }
  .main_center {
    position: absolute;
    width:50px;
    
  }
  .main_right {
    position: relative;
    width:800px;
  }
  .login_dialog {
    width:1000px;
    background-color: #fff;
    box-sizing: border-box;
    border: 1px solid black;
    position: absolute;
    top: 0;
  }
  .dialog_content {
    display: flex;
    justify-content: space-evenly;
  }
  .login_button {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .download_sketch {
    margin: 10px auto;
    width: 230px;
    height: 50px;
    font-size: 18px;
    text-align: center;
    line-height: 50px;
    background-color: #04DDA3;
    border-radius:25px 0 25px 25px;
  }
</style>