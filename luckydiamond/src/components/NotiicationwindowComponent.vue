<template>
  <div class="notification" v-if="notification">
    <div class="notification__content">
      <h3>{{ text }}</h3>
    </div>
  </div>
</template>

<script>
import '@/assets/css/ComponentsStyles/notification.css'

export default {
  props: {
    notification: Boolean,
    text: String,
  },
  emits: ['notificationremove'],
  methods: {
    NotificationsTimer() {
      setTimeout(() => {
        this.$emit('notificationremove')
      }, 4000)
    }
  },
  watch: {
    notification(newVal, oldVal) {
      if (newVal !== oldVal) {
        this.NotificationsTimer()
      }
    }
  }
}
</script>

<style>

</style>