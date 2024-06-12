<template>
  <div class="timer-container">
    <h2 class="text-2xl leading-7 font-semibold">
        和 <a href="https://t.me/purolle" target="_blank"  style="color: black" class="button--doc text-green-500 hover:underline">@Purofle</a> 已经相恋
      </h2>
    <div class="timer">{{ formattedTime }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      startTime: new Date('2024-05-21T00:00:00Z'), // 固定的开始时间
      currentTime: new Date(),
      timer: null
    }
  },
  computed: {
    formattedTime() {
      const diff = Math.floor((this.currentTime - this.startTime) / 1000);
      const days = Math.floor(diff / (3600 * 24));
      const hours = Math.floor((diff % (3600 * 24)) / 3600);
      const minutes = Math.floor((diff % 3600) / 60);
      const seconds = diff % 60;
      return (
        (days < 10 ? '0' + days : days) + '天 ' +
        (hours < 10 ? '0' + hours : hours) + '小时 ' +
        (minutes < 10 ? '0' + minutes : minutes) + '分钟 ' +
        (seconds < 10 ? '0' + seconds : seconds) + '秒'
      );
    }
  },
  methods: {
    updateTime() {
      this.currentTime = new Date();
    }
  },
  mounted() {
    this.timer = setInterval(this.updateTime, 1000);
  },
  beforeDestroy() {
    clearInterval(this.timer);
  }
}
</script>

<style scoped>
.timer-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}
.timer {
  font-size: 48px;
  margin-bottom: 20px;
}

</style>
