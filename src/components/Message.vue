<template>
  <div :class="messageAlignmentClass">
    <div class="message-body message-left" :class="messageColorClass">
      <h5>Ich {{ message.person }}</h5>
      <p>{{ message.text }}</p>
    </div>
    <p class="time">{{ formatTime(message.zeit.seconds) }}</p>
  </div>
</template>

<script>
import moment from 'moment'

export default {
  name: "Message",
  props: {
    message: {
      required: true,
      type: Object
    }
  },
  methods: {
    formatTime(string) {
      console.log(moment.utc(string * 1000))
      return moment.utc(string * 1000).add(moment.duration(1, 'hours')).format('d.M.YY, hh:mm') + ' Uhr'
    }
  },
  computed: {
    messageColorClass() {
      if (this.message.person === 1) {
        return 'color-cyan align-msg-left';
      } else if (this.message.person === 2) {
        return 'color-rose align-msg-right';
      }
      return 'color-yellow align-msg-left'
    },
    messageAlignmentClass() {
      if (this.message.person === 1) {
        return 'align-msg-left';
      } else if (this.message.person === 2) {
        return 'align-msg-right';
      }
      return 'align-msg-left'
    },
  }
}
</script>

<style scoped>
.message-body {
  background-color: #00FFBC;
  padding-top: 10px;
  margin-bottom: 5px;
  width: 330px;
}

.message-body p {
  padding-left: 15px;
  padding-right: 15px;
  line-height: 1.1em;
}

.message-body h5 {
  padding-left: 15px;
  padding-right: 15px;
  font-size: 15px;
  margin-bottom: 3px;
}

.time {
  font-size: 12px;
  text-align: left;
  color: #000;
}

.align-msg-left .time {
  text-align: left;
  margin-left: 5px;
}

.align-msg-right .time {
  text-align: right;
  margin-right: 5px;
}

.align-msg-left {
  float: left;
  text-align: left;
  border-radius: 15px 15px 15px 0px;
}

.align-msg-right {
  float: right;
  text-align: right;
  border-radius: 15px 15px 0px 15px;
}

.color-cyan {
  /*background-color: #00FFBC;*/
  background-color: #167C74;
  color: #fff;
}

.color-rose {
  /*background-color: #f662ab;*/
  /*background-color: #8fe5cf;*/
  background-color: #00B2B2;
  /*color: #fff;*/
  color: #000;
}

.color-yellow {
  /*background-color: #FFFF00;*/
  /*background-color: #00ff90;*/
  background-color: #00FFD3;
  color: #000;
}
</style>