<template>
  <div>
    <button open-type="getUserInfo" lang="zh_CN" @getuserinfo="onGotUserInfo">获取用户信息</button>
    <br>
    用户头像：<img class="userinfo-avatar" :src="userMsg.avatarUrl" alt="">
    <br>
    用户名：<span>{{userMsg.nickName}}</span>
    <br>
    用户所在国家：<span>{{userMsg.country}}</span>
    <br>
    用户所在省份：<span>{{userMsg.province}}</span>
    <br>
    用户所使用的语言：<span>{{userMsg.language}}</span>
  </div>
</template>

<script>

export default {
  data () {
    return {
      userMsg:''
    }
  },
  methods:{
      onGotUserInfo: function(e) {
        this.userMsg = e.mp.detail.userInfo;
      console.log(e)
    }
  }
}
</script>

<style scoped>
.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}
</style>
