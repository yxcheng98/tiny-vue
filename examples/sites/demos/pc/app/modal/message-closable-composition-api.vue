<template>
  <div class="content">
    <tiny-button @click="showModal" :reset-time="0">关闭按钮示例</tiny-button>
  </div>
</template>

<script setup>
import { Button as TinyButton, Modal, Notify } from '@opentiny/vue'

function showModal() {
  Modal.message({
    message: '右侧显示关闭按钮',
    status: 'info',
    messageClosable: true,
    events: {
      close: () => {
        Notify({
          type: 'info',
          title: '触发close回调事件',
          position: 'top-right'
        })
      }
    }
  })
}
</script>
