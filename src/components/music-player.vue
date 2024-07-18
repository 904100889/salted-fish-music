<template>
  <div class="music-player">
    <div class="music-player-detail">
      <img :src="currentTrack.logo" alt="" :class="{'rotating': isPlaying}">
      <h2 class="ml-tiny">{{ currentTrack.title }}
        <span class="music-player-author">-{{ currentTrack.author }}</span>
      </h2>
    </div>
    <div class="music-player-main">
      <audio ref="audio" :src="currentTrack.src" @timeupdate="updateTime" @ended="playNext"></audio>
      <div class="controls">
        <div class="controls-btn">
          <!-- <el-icon class="mr-medium" size="25"><Back /></el-icon> -->
          <el-icon @click="togglePlay" size="30" v-if="isPlaying"><VideoPause /></el-icon>
          <el-icon @click="togglePlay" size="30" v-else><VideoPlay /></el-icon>
          <el-icon @click="playNext" class="ml-medium" size="25"><Right /></el-icon>
        </div>
        <div class="controls-progress">
          <span>{{ formatTime(currentTime) }}</span>
          <div class="mt-step">
            <el-progress :show-text="false" :percentage="progressValue" status="exception" />
          </div>
          <span>{{ formatTime(duration) }}</span>
        </div>
      </div>
    </div>
    <div class="music-player-tool">
      <el-icon size="20"><Headset /></el-icon>
      <!-- <div class="playlist">
        <h3>Playlist</h3>
        <ul>
          <li v-for="(track, index) in tarckList" :key="index" :class="{ active: index === currentTrackIndex }" @click="selectTrack(index)">
            {{ track.title }}
          </li>
        </ul>
      </div> -->
    </div>
  </div>
</template>

<script lang="ts" setup>
import {ref, computed, onMounted} from 'vue'

interface Tarck {
  title: string,
  logo: string,
  src: string,
  author: string
}

const tarckList: Tarck[] = [
  {title: '直到世界终结', logo: '/src/assets/images/logo.jpg', src: '/music/4.mp3', author: 'rcw'},
  {title: '飘向北方', logo: '/src/assets/images/logo.jpg', src: '/music/3.mp3', author: 'czh'},
  {title: '七里香', logo: '/src/assets/images/logo.jpg', src: '/music/2.mp3', author: 'jht'},
  {title: '亲爱的, 那不是爱情', logo: '/src/assets/images/logo.jpg', src: '/music/1.mp3', author: 'rcw'}
]

const currentTrackIndex = ref(0)
const currentTrack = computed(() => tarckList[currentTrackIndex.value]);

const isPlaying = ref(false)
const currentTime = ref(0)
const duration = ref(0)
const progressValue = ref(0)
const audio = ref<HTMLAudioElement | null>(null)

const togglePlay = () => {
  if (!audio.value) {
    return
  }

  if (isPlaying.value) {
    audio.value.pause()
  } else {
    audio.value.play()
  }

  isPlaying.value = !isPlaying.value
}

const updateTime = () => {
  if (!audio.value) return
  currentTime.value = audio.value.currentTime
  duration.value = audio.value.duration
  progressValue.value = (currentTime.value / duration.value * 100) || 0
}

const playNext = () => {
  // 切换歌曲 % length 防止下标超出 例如2%3 = 2 3%3 = 0
  currentTrackIndex.value = (currentTrackIndex.value + 1) % tarckList.length
  if (!audio.value) return

  audio.value.load()
  setTimeout(() => {
    audio.value!.play()
  }, 100)
  isPlaying.value = true
}

const formatTime = (time: number) => {
  const minutes = Math.floor(time / 60)
  const seconds = Math.floor(time % 60).toString().padStart(2, '0')
  return `${minutes}:${seconds}`
}

const selectTrack = (index: number) => {
  currentTrackIndex.value = index
  if (audio.value) {
    audio.value.load()
    audio.value.play()
    isPlaying.value = true
  }
}

onMounted(() => {
  if (audio.value) {
    audio.value.addEventListener('loadedmetadata', () => {
      duration.value = audio.value!.duration
    })
  }
})
</script>

<style>
  .music-player {
    display: flex;
    position: absolute;
    z-index: 1;
    left: 0;
    bottom: 0;
    align-items: center;
    padding: 0 30px;
    width: 100%;
    height: 80px;
    background-color: #fafafa;
  }

  .music-player-detail {
    flex: 4;
    display: flex;
    align-items: center;
  }

  .music-player-detail > img {
    height: 60px;
    width: 60px;
    border-radius: 30px;
    transition: transform 5s linear;
  }

  .music-player-tool {
    text-align: right;
    flex: 4;
  }

  .music-player-main {
    flex: 6;
  }

  .music-player .controls {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .controls-btn {
    text-align: center;
  }

  .controls-progress {
    display: flex;
  }

  .controls-progress > span {
    flex: 1;
    font-size: 12px;
    text-align: center;
    color: #999;
  }

  .controls-progress > div {
    flex: 12;
  }

  .music-player-author {
    vertical-align: middle;
    font-size: 14px;
    color: #666;
  }

  .rotating {
    animation: rotation 30s infinite linear;
  }

  @keyframes rotation {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(360deg);
    }
  }

</style>
