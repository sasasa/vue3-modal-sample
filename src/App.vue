<template>
  <button @click="openModal">Click</button>

  <div id="overlay" v-show="showContent" @click.self="closeModal">
    <div id="content">
      <p>これがモーダルウィンドウです。</p>
      <button @click="closeModal">Close</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const showContent = ref(false);

const openModal = () => {
  showContent.value = true;
};

const closeModal = () => {
  showContent.value = false;
};
</script>

  <style>
#overlay {
  /*　要素を重ねた時の順番　*/
  z-index: 1;

  /*　画面全体を覆う設定　*/
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);

  /*　画面の中央に要素を表示させる設定　*/
  display: flex;
  align-items: center;
  justify-content: center;
}

#content {
  z-index: 2;
  width: 50%;
  padding: 1em;
  background: #fff;
}
</style>
