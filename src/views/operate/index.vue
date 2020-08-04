<template>
    <div class="operate_container">
        <div class="operate_header">
            云运维平台
        </div>
        <div class="operate_body">
            <div class="operate_message">
                <div class="message_header"><i class="message_title">项目人员信息</i><i class="message_record">(52条记录)</i>
                    <span class="message_count" style="line-height: 40px;">故障：<i class="message_fault">14</i>异常：<i class="message_abnormal">21</i></span>
                </div>
                <div class="message_body">
                    <table class="message_table">
                        <tbody>
                            <tr class="messages" :key="index" v-for="(item,index) in messages">
                                <td class="item_dot"><i :class="item.isRed? 'redDot' : 'orangeDot'"></i></td>
                                <td class="item_info">{{item.info}}</td>
                                <td class="item_timer">{{item.timer}}</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
            <div class="operate_monitor">
                <div class="monitor_header"><i class="monitor_title">数据监控</i>
                    <span class="monitor_stopwatch">
                        <el-date-picker
                            v-model="value"
                            type="daterange"
                            range-separator="至"
                            start-placeholder="开始日期"
                            end-placeholder="结束日期">
                        </el-date-picker>
                    </span>
                </div>
                <div class="monitor_body">
                    <div class="monitor_button">
                        <el-button type="primary">子系统操作系统</el-button>
                        <el-button type="info">子系统运行日志</el-button>
                        <el-button type="info">终端状态日志</el-button>
                        <el-button type="info">终端运行日志</el-button>
                    </div>
                    <table class="monitor_table">
                        <tbody class="monitor_tbody">
                            <tr class="monitors" :key="index" v-for="(item,index) in monitors">
                                <td class="item.school">{{item.school}}</td>
                                <td class="item.user">{{item.user}}</td>
                                <td class="item.ip">{{item.ip}}</td>
                                <td class="item.module">{{item.module}}</td>
                                <td class="item.content">{{item.content}}</td>
                                <td class="item.time">{{item.time}}</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
            <div class="operate_status">
                <div class="operate_node">
                    <div class="node_header"><i class="node_title">节点状态</i></div>
                    <div class="node_body">
                        <div class="text_1"><i>设备1工作中:</i>
                          <div class="chart_1">
                            <div class="aaa"><chart-one></chart-one><span>ip占用</span></div>
                            <div class="bbb"><chart-two></chart-two><span>CPU占用</span></div>
                            <div class="ccc"><chart-three></chart-three><span>内存占用</span></div>
                            <div class="ddd"><chart-four></chart-four><span>磁盘占用</span></div>
                          </div>
                        </div>
                        <div class="text_2"><i>设备2工作中:</i>
                          <div class="chart_2">
                            <div class="aaa"><chart-one></chart-one><span>ip占用</span></div>
                            <div class="bbb"><chart-two></chart-two><span>CPU占用</span></div>
                            <div class="ccc"><chart-three></chart-three><span>内存占用</span></div>
                            <div class="ddd"><chart-four></chart-four><span>磁盘占用</span></div>
                            </div>
                        </div>
                        <div class="text_3"><i>设备3工作中:</i>
                          <div class="chart_3">
                            <div class="aaa"><chart-one></chart-one><span>ip占用</span></div>
                            <div class="bbb"><chart-two></chart-two><span>CPU占用</span></div>
                            <div class="ccc"><chart-three></chart-three><span>内存占用</span></div>
                            <div class="ddd"><chart-four></chart-four><span>磁盘占用</span></div>
                          </div>
                        </div>
                    </div>
                </div>
                <div class="operate_service">
                    <div class="service_header"><i class="service_title">服务状态</i></div>
                    <div class="service_body">
                        <table class="service_table">
                            <tbody class="service_tbody">
                                <tr class="services" :key="index" v-for="(item,index) in services">
                                    <td :class="[item.status == '0' ? 'green' : '',item.status == '1' ? 'yellow' : '',item.status == '2' ? 'red' : '']">{{item.equipment}}</td>
                                    <td class="item_reason">{{item.reason}}</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import ChartOne from './charts/chart1'
import ChartTwo from './charts/chart2'
import ChartThree from './charts/chart3'
import ChartFour from './charts/chart4'
export default {
  name: 'chart',
  components: { ChartOne, ChartTwo, ChartThree, ChartFour },
  component:
  ChartOne,
  ChartTwo,
  ChartThree,
  ChartFour,
  data () {
    return {
      messages: [{
        info: '开机无显示',
        timer: '2020-02-20',
        isRed: true
      },
      {
        info: '频繁死机',
        timer: '2020-02-20',
        isRed: false
      },
      {
        info: '设置不能保存',
        timer: '2020-02-20',
        isRed: true
      },
      {
        info: '开机无显示',
        timer: '2020-02-20',
        isRed: true
      },
      {
        info: '频繁死机',
        timer: '2020-02-20',
        isRed: false
      },
      {
        info: '设置不能保存',
        timer: '2020-02-20',
        isRed: true
      },
      {
        info: '开机无显示',
        timer: '2020-02-20',
        isRed: true
      },
      {
        info: '频繁死机',
        timer: '2020-02-20',
        isRed: false
      },
      {
        info: '设置不能保存',
        timer: '2020-02-20',
        isRed: true
      }],
      value: '',
      monitors: [{
        school: '归属学校',
        user: '操作人',
        ip: '操作IP',
        module: '操作模块',
        content: '操作内容',
        time: '操作时间'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      },
      {
        school: '福建师范大学',
        user: '陈麟琳',
        ip: '192.1.11.111',
        module: '设置-个人信息-账号信息',
        content: '修改账户信息',
        time: '2020-05-02 14:00:00'
      }],
      services: [{
        equipment: '设备1:',
        reason: '内存不足',
        status: '0'
      },
      {
        equipment: '设备1:',
        reason: 'CPU占用大',
        status: '0'
      },
      {
        equipment: '设备2:',
        reason: '时间循环延迟',
        status: '1'
      },
      {
        equipment: '设备2:',
        reason: '时间循环延迟',
        status: '1'
      },
      {
        equipment: '设备2:',
        reason: '时间循环延迟',
        status: '1'
      },
      {
        equipment: '设备2:',
        reason: '时间循环延迟',
        status: '1'
      },
      {
        equipment: '设备3:',
        reason: '应急时间详细内容',
        status: '2'
      },
      {
        equipment: '设备3:',
        reason: '应急时间详细内容',
        status: '2'
      }],
      items: [{
        value1: 20,
        value2: 80
      },
      {
        value1: 30,
        value2: 70
      },
      {
        value1: 40,
        value2: 60
      },
      {
        value1: 50,
        value2: 50
      }]
    }
  }
}
</script>

<style lang="less" scoped>
.operate_container {
    display: flex;
    flex-direction: column;
    background-color: #070C20;
    height: 100%;
    width: 100%;
    padding: 0;
}
.operate_header {
    display: flex;
    justify-content: center;
    color: #51FFFE;
    font-size: 45px;
    letter-spacing: 10px;
    height: 125px;
}
.operate_body {
    display: flex;
    flex-direction: row;
}
.operate_message {
    display: flex;
    justify-content: flex-start;
    flex-direction: column;
    height: 935px;
    width: 540px;
    border: 1px;
    background-color: #051634;
    margin-left: 15px;
}
.message_header {
    height: 50px;
    width: 100%;
    background-color: #08304A;
    line-height: 50px;

    .message_title {
    margin-left: 20px;
    font-size: 20px;
    color: #00EEFF;
    font-style: normal;
    }

    .message_record {
    font-size: 15px;
    color: #00A0EC;
    font-style: normal;
    }
}
.message_count {
    float: right;
    font-size: 16px;
    color: #eee;
    padding-right: 20px;

    .message_fault {
    font-size: 20px;
    color: #FF0048;
    margin-right: 25px;
    line-height: 50px;
    font-style: normal;
    }
    .message_abnormal {
    font-size: 20px;
    color: #FF6602;
    font-style: normal;
    }
}
.message_body {
    width: 100%;
    height: 100%;
}
table {
    width: 100%;
}
.item_dot {
    float: left;
    padding: 0;
    height: 50px;
    width: 10px;
    line-height: 10px;
    margin-left: 20px;

    .redDot {
    display: block;
    background-color: #FF0048;
    height: 10px;
    width: 10px;
    border-radius: 50%;
    margin-top: 20px;
    }
    .orangeDot {
    display: block;
    background-color: #FF6602;
    height: 10px;
    width: 10px;
    border-radius: 50%;
    margin-top: 20px;
    }
}
.item_info {
    color: #eee;
    float: left;
    padding: 0;
    margin-left: 10px;
    height: 50px;
    width: 100px;
    line-height: 50px;
}
.item_timer {
    float: right;
    color: #eee;
    height: 50px;
    width: 100px;
    line-height: 50px;
    margin-right: 20px;
}
.operate_monitor {
    display: flex;
    justify-content: center;
    flex-direction: column;
    height: 935px;
    width: 1000px;
    border: 1px;
    background-color: #051634;
    margin-left: 10px;
}
.monitor_header {
    height: 50px;
    width: 100%;
    background-color: #08304A;
    line-height: 50px;

    .monitor_title {
    margin-left: 20px;
    font-size: 20px;
    color: #00EEFF;
    font-style: normal;
    }
    .monitor_stopwatch {
    float: right;
    font-size: 16px;
    color: #eee;
    padding-right: 20px;
    }
}
.monitor_body {
    height: 100%;
    width: 100%;
}
.monitor_button {
    height: 35px;
    text-align: center;
    margin: 20px;

    .el-button {
    height: 35px;
    width: 150px;
    margin: 0 10px;
    }
    .el-button--primary {
    background-color: #51FFFE;
    color: black;
    }
    .el-button--info {
    background-color: #031636;
    color: #51FFFE;
    border-color: #51FFFE;
    }
}
.monitor_table {
    color: #eee;
    width: 100%;
    padding: 0;
    text-align: center;
    border-collapse: collapse;
}
.monitors {
    height: 50px;
}
.monitors:nth-child(2n){
    background: #152C4C;
}
.monitors td {
    border: 0px solid;
}
.operate_status {
    display: flex;
    justify-content: flex-end;
    flex-direction: column;
}
.operate_node {
    height: 580px;
    width: 540px;
    border: 1px;
    background-color: #051634;
    margin-left: 10px;
}
.node_header {
    height: 50px;
    width: 100%;
    background-color: #08304A;
    line-height: 50px;

    .node_title {
    margin-left: 20px;
    font-size: 20px;
    color: #00EEFF;
    font-style: normal;
    }
}
.node_body {
    height: 100%;
    width: 100%;
}
.text_1 {
  display: flex;
  flex-direction: column;
  color: #eee;
  padding-left: 20px;
  height: 150px;
  i {
    margin-top: 20px;
  }
  .chart_1 {
    margin-top: 20px;
    display: flex;
    flex-direction: row;
  }
}
.text_2 {
  display: flex;
  flex-direction: column;
  color: #eee;
  padding-left: 20px;
  height: 150px;
  i {
    margin-top: 20px;
  }
  .chart_2 {
    margin-top: 20px;
    display: flex;
    flex-direction: row;
  }
}
.text_3 {
  display: flex;
  flex-direction: column;
  color: #eee;
  padding-left: 20px;
  height: 150px;
  i {
    margin-top: 20px;
  }
  .chart_3 {
    margin-top: 20px;
    display: flex;
    flex-direction: row;
  }
}
.aaa {
  margin: 0 15px;
}
.bbb {
  margin: 0 15px;
}
.ccc {
  margin: 0 15px;
}
.ddd {
  margin: 0 15px;
}
.operate_service {
    width: 540px;
    height: 345px;
    border: 1px;
    background-color: #051634;
    margin:10px 0 0 10px;
}
.service_header {
    height: 50px;
    width: 100%;
    background-color: #08304A;
    line-height: 50px;

    .service_title {
    margin-left: 20px;
    font-size: 20px;
    color: #00EEFF;
    font-style: normal;
    }
}
.service_body {
    padding-left: 20px;
}
.service_table {
    color: #eee;
    border-collapse: collapse;
    border-spacing: 10px;
}
.services {
    height: 35px;
    border-bottom: 1px dashed #eee;
}
.green {
  width: 50px;
  color: #3CB685
}
.yellow {
  width: 50px;
  color: #BC9362
}
.red {
  width: 50px;
  color: #B63741
}
</style>