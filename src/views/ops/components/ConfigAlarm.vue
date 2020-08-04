<template>
    <div class="body_left">
        <div class="left_header">
            <span class="alarm_title">配置警告</span>
            <span class="alarm_count">({{alarmForm.length}}条记录)</span>
            <div class="bug">
                <span class="alarm_bug">故障：<i class="alarm_fault">{{alarmForm.length}}</i></span>
                <span class="alarm_bug">异常：<i class="alarm_abnormal">{{alarmForm.length}}</i></span>
            </div>

        </div>
        <div class="left-body">
            <liquid-fill></liquid-fill>
        </div>
    </div>
</template>

<script>
import LiquidFill from './LiquidFill'
export default {
  components: {
    LiquidFill
  },
  data () {
    return {
      alarmForm: [
        {
          news: '设备1开机无显示',
          time: '2020-02-20'
        },
        {
          news: '设备1频繁死机',
          time: '2020-02-20'
        },
        {
          news: '设备1设置不能保存',
          time: '2020-02-20'
        },
        {
          news: '设备1开机无显示',
          time: '2020-02-20'
        },
        {
          news: '设备1频繁死机',
          time: '2020-02-20'
        },
        {
          news: '设备1设置不能保存',
          time: '2020-02-20'
        },
        {
          news: '设备1开机无显示',
          time: '2020-02-20'
        }
      ]
    }
  }
}
</script>

<style lang="less" scoped>
.body_left {
    width: 24.74%;
    height: 95.5%;
    margin: 20px 15px 0px 14px;
    background:rgba(1,51,102,0.3);
    border:1px solid rgba(0, 0, 0, 1);
    .left_header {
        width:100%;
        height:5.35%;
        background:rgba(1,86,152,0.3);
        border:1px solid rgba(28, 72, 122, 1);
        .alarm_title {
            width:19.16%;
            height:42%;
            font-size:0.55rem;
            font-family:Source Han Sans CN;
            font-weight:bold;
            color:rgba(0,229,255,1);
            line-height:36px;
            margin: 0px 10px 0px 17px;
            letter-spacing: 2px;
        }
        .alarm_count {
            width:18.95%;
            height:40%;
            font-size:0.45rem;
            font-family:Source Han Sans CN;
            font-weight:400;
            color:rgba(2,170,253,1);
            line-height:36px;
            letter-spacing: 2px;
        }
        .bug {
            float: right;
            .alarm_bug {
            font-size:0.4rem;
            font-family:Source Han Sans CN;
            font-weight:400;
            color:rgba(255,255,255,1);
            padding-right: 15px;
            line-height: 50px;
                .alarm_fault {
                    font-size:0.55rem;
                    font-family:Arial;
                    font-weight:400;
                    color:rgba(255,0,72,1);
                    line-height: 50px;
                }
                .alarm_abnormal {
                    font-size:0.55rem;
                    font-family:Arial;
                    font-weight:400;
                    color:rgba(255,102,0,1);
                }
            }
        }
    }
    .left-body {
        width: 100%;
        height: 94.65%;
    }
}
</style>
