<template>
  <div class="outer-container">
    <div class="layout">
      <div class="timer-container">
        <div class="image">
          <div class="code002">
            <a href="https://t.me/buchhuanpangci" target="_blank">
              <img src="public\articles\CODE002.jpg">
            </a>
            <div>CODE:002</div>
          </div>
          <div class="love">
            <img src="public/articles/Love.png">
          </div>
          <div class="purofle">
            <a href="https://t.me/purolle" target="_blank">
              <img src="public\articles\Purofel.jpg">
            </a>
            <div>Purofle</div>
          </div>
        </div>
          <h2 class="text1">
            我们已经相恋了：
          </h2>
        <div class="timer">{{ formattedTime }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      startTime: new Date("2024-05-21T00:00:00Z"), // 固定的开始时间
      currentTime: new Date(),
      timer: null,
    };
  },
  computed: {
    formattedTime() {
      const diff = Math.floor((this.currentTime - this.startTime) / 1000);
      const days = Math.floor(diff / (3600 * 24));
      const hours = Math.floor((diff % (3600 * 24)) / 3600);
      const minutes = Math.floor((diff % 3600) / 60);
      const seconds = diff % 60;
      return (
        (days < 10 ? "0" + days : days) +
        " 天 " +
        (hours < 10 ? "0" + hours : hours) +
        " 小时 " +
        (minutes < 10 ? "0" + minutes : minutes) +
        " 分 " +
        (seconds < 10 ? "0" + seconds : seconds) +
        " 秒"
      );
    },
  },
  methods: {
    updateTime() {
      this.currentTime = new Date();
    },
  },
  mounted() {
    this.timer = setInterval(this.updateTime, 1000);
  },
  beforeDestroy() {
    clearInterval(this.timer);
  },
};
</script>

<style scoped>
html, body {
  margin: 0;
  padding: 0;
  height: 100%;
  overflow: hidden; /* 隐藏滚动条 */
}

.outer-container {
  display: inline-block;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%); /* 使用 transform 实现垂直和水平居中 */
  display: flex; /* 使用弹性布局 */
  justify-content: center; /* 水平居中对齐 */
  align-items: center; /* 垂直居中对齐 */
  height: 100vh; /* 使容器高度占满整个视口 */
}

.layout {
  display: inline-block; /* 使用 inline-block 使元素的宽度根据内容自动调整 */
  width: auto; /* 重置内容宽度，使其根据内容自动调整 */
  text-align: left; /* 恢复文字居左显示 */
  margin: 0; /* 重置边距 */
  margin-left: 15px; /* 设置左边距为 15 像素 */
  height: auto; /* 重置内容高度，使其根据内容自动调整 */
}

.timer-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: auto;
}

.timer {
  font-size: 48px;
  margin-bottom: 20px;
  display: flex;
  width: auto;
  height: auto;
}

.image {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row; /* 让容器在一行显示 */
  justify-content: space-between; /* 在一行上均匀分布 */
}

.code002, .purofle {
  text-align: center /* 使图片和说明文字居中 */
}

.code002 img, .purofle img {
  width: 100px;
  height: 100px;
  border-radius: 50%;
}

.love img {
  width: 110px;
  height: 110px;
  object-fit: cover;
  object-position: center;
}

@media (max-width: 1300px) {
  .outer-container {
    flex-direction: column; /* 在小屏幕上垂直排列 */
    height: auto; /* 允许容器高度自动调整 */
  }

  .layout {
    width: 100%; /* 使布局宽度占满屏幕 */
    margin: 0; /* 重置边距 */
    padding: 10px; /* 添加内边距 */
  }

  .timer {
    font-size: 30px; /* 调整字体大小 */
    margin-bottom: 10px; /* 调整底部边距 */
  }

  .code002 img, .purofle img {
    width: 90px; /* 调整图片宽度 */
    height: 90px; /* 调整图片高度 */
  }

  .love img {
  width: 95px;
  height: 95px;
  object-fit: cover;
  object-position: center;
  }
}

@media (max-width: 800px) {
  .outer-container {
    flex-direction: column; /* 在小屏幕上垂直排列 */
    height: auto; /* 允许容器高度自动调整 */
  }

  .layout {
    width: 100%; /* 使布局宽度占满屏幕 */
    margin: 0; /* 重置边距 */
    padding: 10px; /* 添加内边距 */
  }

  .timer {
    font-size: 20px; /* 调整字体大小 */
    margin-bottom: 10px; /* 调整底部边距 */
  }

  .code002 img, .purofle img {
    width: 60px; /* 调整图片宽度 */
    height: 60px; /* 调整图片高度 */
  }

  .love img {
  width: 65px;
  height: 65px;
  object-fit: cover;
  object-position: center;
  }
  .code002, .purofle {
  text-align: center; /* 使图片和说明文字居中 */
  font-size: 12px;
  }
}

@media (max-width: 520px) {
  .outer-container {
    flex-direction: column; /* 在小屏幕上垂直排列 */
    height: auto; /* 允许容器高度自动调整 */
  }

  .layout {
    width: 100%; /* 使布局宽度占满屏幕 */
    margin: 0; /* 重置边距 */
    padding: 10px; /* 添加内边距 */
  }

  .timer {
    font-size: 18px; /* 调整字体大小 */
    margin-bottom: 10px; /* 调整底部边距 */
  }

  .code002 img, .purofle img {
    width: 55px; /* 调整图片宽度 */
    height: 55px; /* 调整图片高度 */
  }

  .love img {
  width: 60px;
  height: 60px;
  object-fit: cover;
  object-position: center;
  }

  .code002, .purofle {
  text-align: center; /* 使图片和说明文字居中 */
  font-size: 12px;
  }
}

@media (max-width: 430px) {
  .outer-container {
    flex-direction: column; /* 在小屏幕上垂直排列 */
    height: auto; /* 允许容器高度自动调整 */
  }

  .layout {
    width: 100%; /* 使布局宽度占满屏幕 */
    margin: 0; /* 重置边距 */
    padding: 10px; /* 添加内边距 */
  }

  .timer {
    font-size: 16px; /* 调整字体大小 */
    margin-bottom: 10px; /* 调整底部边距 */
  }

  .code002 img, .purofle img {
    width: 55px; /* 调整图片宽度 */
    height: 55px; /* 调整图片高度 */
  }

  .love img {
  width: 60px;
  height: 60px;
  object-fit: cover;
  object-position: center;
  }

  .code002, .purofle {
  text-align: center; /* 使图片和说明文字居中 */
  font-size: 12px;
  }
  .text1 {
  font-size: 22px;
  }
}

@media (max-width: 360px) {
  .outer-container {
    flex-direction: column; /* 在小屏幕上垂直排列 */
    height: auto; /* 允许容器高度自动调整 */
  }

  .layout {
    width: 100%; /* 使布局宽度占满屏幕 */
    margin: 0; /* 重置边距 */
    padding: 10px; /* 添加内边距 */
  }

  .timer {
    font-size: 15px; /* 调整字体大小 */
    margin-bottom: 10px; /* 调整底部边距 */
  }

  .code002 img, .purofle img {
    width: 55px; /* 调整图片宽度 */
    height: 55px; /* 调整图片高度 */
  }

  .love img {
  width: 60px;
  height: 60px;
  object-fit: cover;
  object-position: center;
  }

  .code002, .purofle {
  text-align: center; /* 使图片和说明文字居中 */
  font-size: 10px;
  }

  .text1 {
  font-size: 20px;
  }
}
</style>
