<template>
    <div class="ops_container">
        <div id="ops_bg"></div>
        <div class="ops_header">
            <div class="header_title">云运维平台</div>
            <div class="header_options" @click="setUp()">
                <img src="./src/if_icons_settings_1564529 (1).png" alt=""><span>设置</span>
            </div>
        </div>
        <div class="ops_body">
            <div class="body_center">
                <div class="center_top">
                    <div class="top_header"></div>
                    <div class="top_body"></div>
                </div>
                <div class="center_bottom">
                    <div class="bottom_header"></div>
                    <div class="bottom_body"></div>
                </div>
            </div>
            <div class="body_right">
                <div class="right_header"></div>
            </div>
        </div>
    </div>
</template>

<script>
import rem from 'src\assets\rem.js'
import ConfigAlarm from './components/ConfigAlarm'
export default {
  components: { ConfigAlarm },
  data () {
    return {
    }
  },
  methods: {
    setUp () {
      console.log('设置')
      console.log('rem', rem)
    }
  }
}
</script>

<style lang="less" scoped>
@font-face {
    font-family: PangMenZhengDao;
    src: url('./src/庞门正道标题体.TTF');
}
.ops_container {
    height: 100%;
    width: 100%;
    padding: 0;
    margin: 0 auto;
    zoom: 1;
    overflow: auto;
    #ops_bg {
        position:fixed;
        top: 0;
        left: 0;
        width:100%;
        height:100%;
        z-index:-1000;
        background-image: url('./src/背景.png');
        background-color: #fff;
        background-repeat: no-repeat;
        background-position: center 0;
    }
}

.ops_header {
    width: 100%;
    height: 9.81%;
    text-align: center;
    overflow: hidden;
    z-index: 1000;
    background: url('./src/标题背景.png');
    background-repeat: no-repeat;
    background-position: center 0;
    .header_title {
        margin: auto;
        transform: translateY(30%);
        font-size: 1.525rem;
        font-family:PangMenZhengDao;
        letter-spacing: 10px;
        color:rgba(82,255,255,1);
    }
    .header_options {
        position: absolute;
        top: 5.65%;
        left: 94.58%;
        line-height:30px;
        img {
            display: inline-block;
            vertical-align: middle;
        }
        span {
            font-size:0.5rem;
            font-family:Source Han Sans CN;
            font-weight:400;
            color:rgba(82,255,255,1);

        }
    }
}
.ops_body {
    display: flex;
    width: 100%;
    height: 90.19%;
    .body_center {
        width: 47.66%;
        height: 95.5%;
        flex-direction: column;
        margin: 20px 0px 0px 0px;
        .center_top {
            width: 100%;
            height: 63.2%;
            background:rgba(1,51,102,1);
            border:1px solid rgba(0, 0, 0, 1);
            opacity:0.4;
            .top_header {
                width:100%;
                height:8.59%;
                background:rgba(1,86,152,1);
                border:1px solid rgba(28, 72, 122, 1);
            }
        }
        .center_bottom {
            width: 100%;
            height: 35.6%;
            background:rgba(1,51,102,1);
            border:1px solid rgba(0, 0, 0, 1);
            opacity:0.4;
            margin-top: 1.2%;
            .bottom_header {
                width:100%;
                height:14.71%;
                background:rgba(1,86,152,1);
                border:1px solid rgba(28, 72, 122, 1);
            }
        }
    }
    .body_right {
        width: 24.74%;
        height: 95.5%;
        margin: 20px 14px 0px 15px;
        background:rgba(1,51,102,1);
        border:1px solid rgba(0, 0, 0, 1);
        opacity:0.3;
        .right_header {
            width:100%;
            height:4.49%;
            background:rgba(1,86,152,1);
            border:1px solid rgba(28, 72, 122, 1);
        }
    }

}
</style>
