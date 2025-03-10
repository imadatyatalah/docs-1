<template>
  <a
    v-if="isVisible"
    id="vs"
    href="https://vueschool.io/sales/price-increase-22?friend=vuejs"
    target="_blank"
    rel="noreferrer"
  >
    <div class="vs-logo">
      <img src="/images/vueschool/vs-iso.svg" class="logo-small">
      <img src="/images/vueschool/vs-logo.svg" class="logo-big">
    </div>
    <div class="vs-core">
      <div class="vs-slogan">
        <div class="vs-slogan-title">
          Get up to <strong>40% off</strong> your Vue School Subscription
        </div>
        <div class="vs-slogan-subtitle">
          Time Limited Offer
        </div>
      </div>
      <div class="vs-button">
        <div class="vs-button-inside">
          GET OFFER
        </div>
      </div>
    </div>
    <div id="vs-close" class="vs-close" @click.stop.prevent="close">
      <img src="/images/vueschool/vs-close.svg" alt="Close">
    </div>
  </a>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const isVisible = ref(false)

onMounted(() => {
  isVisible.value = !localStorage.getItem('VS_FW_22_OFFER')
  if (isVisible.value) document.body.classList.add('has-top-banner')
})

function close () {
  isVisible.value = false
  document.body.classList.remove('has-top-banner')
  localStorage.setItem('VS_FW_22_OFFER', 1)
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

#vs {
  align-items: center;
  background-color: #000c19;
  box-sizing: border-box;
  color: #fff;
  display: flex;
  font-family: 'Roboto', Oxygen, Fira Sans, Helvetica Neue, sans-serif;
  justify-content: center;
  position: fixed;
  padding: 0 10px;
  left: 0;
  right: 0;
  top: 0;
  z-index: 100;
  height: 5rem;
  line-height: 1;
  background-image: url(/images/vueschool/vs-fw-bg-small.svg);
  background-size: cover;
  background-repeat: no-repeat;
}

#vs:hover {
  text-decoration: none;
}

#vs .vs-logo {
  position: absolute;
  left: 20px;
  top: 20px;
}

#vs .vs-logo .logo-big {
  display: none;
}

#vs:hover .vs-core .vs-button-inside {
  background: linear-gradient(257deg, #e19b09 99%, #ffca24 6%);
}

#vs .vs-core .vs-slogan {
  color: #fff;
  margin-left: 8px;
  text-align: center;
}

#vs .vs-core {
  align-items: center;
  display: flex;
  justify-content: center;
}

#vs .vs-core .vs-slogan .vs-slogan-subtitle {
  font-size: 14px;
  color: #cdc5dc;
  margin-top: 8px;
}

#vs .vs-core .vs-slogan .vs-slogan-title {
  font-size: 16px;
  font-weight: 800;
}

#vs .vs-core .vs-slogan .vs-slogan-title strong {
  color: #fdc722;
}

#vs .vs-core .vs-button {
  background: linear-gradient(0deg, #ffdf4c, #e29d0a);
  padding: 2px;
  margin-right: 18px;
  margin-left: 16px;
  border-radius: 30px;
  display: none;
}

#vs .vs-core .vs-button-inside {
  color: #000;
  padding: 7px 10px;
  font-weight: 800;
  font-size: 22px;
  white-space: nowrap;
  border-radius: 30px;
  background: linear-gradient(90deg, #FFC828, #E19C0E);
  text-transform: uppercase;
}

#vs .vs-close {
  right: 6px;
  position: absolute;
}

#vs .vs-close:hover {
  color: #56d8ff;
}

.has-top-banner {
  --vt-banner-height: 80px;
}

.has-top-banner .banner {
  height: 24px;
  line-height: 24px;
  top: 80px;
}

@media (min-width: 680px) {
  #vs {
    background-image: url(/images/vueschool/vs-fw-bg.svg);
    background-position: top right -110px;
  }

  #vs .vs-core .vs-slogan {
    margin-left: 24px;
  }

  #vs .vs-core .vs-slogan .vs-slogan-subtitle {
    font-size: 16px;
  }

  #vs .vs-core .vs-slogan .vs-slogan-title {
    font-size: 18px;
  }

  #vs .vs-core .vs-button {
    display: inline-block;
    margin-right: 0;
    margin-left: 22px;
  }

  #vs .vs-core .vs-button-inside {
    padding: 8px 24px;
  }

  #vs .vs-close {
    padding: 10px;
    right: 20px;
  }
}

@media (min-width: 768px) {
  #vs .vs-logo .logo-small {
    display: none;
  }

  #vs .vs-logo .logo-big {
    display: inline-block;
  }

  #vs .vs-core {
    width: 430px;
  }
}

@media (min-width: 1024px) {
  #vs {
    background-position: top right;
  }

  #vs .vs-core .vs-slogan .vs-slogan-title {
    font-size: 24px;
  }

  #vs .vs-core .vs-button {
    margin-left: 69px;
  }

  #vs .vs-core {
    width: auto;
  }
}
</style>
