cordova plugin add cordova-plugin-calllistener

  ```javascript

  created () {
    setTimeout(function () {
      /* 监听电话状态（1空闲、2响铃、3通话） */
      CallListener.addListener((state) => {
        if (state == 1) {
          /* 获取通话时长（单位秒） */
          CallListener.getCallInfo((info) => {
            Toast.text({
              duration: 3000,
              message: '电话状态：' + state + '，通话时长：' + info.duration + '，开始时间：' + info.startDate + '，结束时间：' + info.endDate
            })
          }, '13207180317')
        } else {
          Toast.text({
            duration: 3000,
            message: '电话状态：' + state
          })
        }
      })
    },1000)
  },

  ```