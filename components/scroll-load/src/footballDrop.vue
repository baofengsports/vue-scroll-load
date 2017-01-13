<template>
    <div class="drop-update">
        <div v-show="dropState === 'drop' || dropState === 'release' || dropState === 'update'" class="sprite juggle">
        </div>
        <div v-show="dropState === 'complete'" class="sprite shot">
        </div>
    </div>
</template>
<script>
import Loading from '../../loading/src/main.vue'

export default {
    data() {
        return {
            dropState: 'drop', // 下拉时的状态，‘drop’－正在下拉， ‘release’－手指释放， ‘update’－正在更新数据，‘complete’－‘数据更新成功’
        }
    },
}
</script>
<style lang="scss" scoped>
.drop-update {
    margin-top: -100px;
    /*px*/
    height: 100px;
    /*px*/
    line-height: 100px;
    /*px*/
    background: #fff;
    text-align: center;
    font-size: 24px;
    /*px*/
    

    @keyframes runJuggle {
        0% {
            background: url("../images/football/juggle/1.png") no-repeat;
            background-size: contain;
        }
        12.5% {
            background: url("../images/football/juggle/2.png") no-repeat;
            background-size: contain;
        }
        25% {
            background: url("../images/football/juggle/3.png") no-repeat;
            background-size: contain;
        }
        37.5% {
            background: url("../images/football/juggle/4.png") no-repeat;
            background-size: contain;
        }
        50% {
            background: url("../images/football/juggle/5.png") no-repeat;
            background-size: contain;
        }
        62.5% {
            background: url("../images/football/juggle/6.png") no-repeat;
            background-size: contain;
        }
        75% {
            background: url("../images/football/juggle/7.png") no-repeat;
            background-size: contain;
        }
        87.5% {
            background: url("../images/football/juggle/8.png") no-repeat;
            background-size: contain;
        }
        100% {
            background: url("../images/football/juggle/1.png") no-repeat;
            background-size: contain;
        }
    }
    @keyframes runShot {
        0% {
            background: url("../images/football/shot/1.png") no-repeat;
            background-size: contain;
        }
        10% {
            background: url("../images/football/shot/2.png") no-repeat;
            background-size: contain;
        }
        20% {
            background: url("../images/football/shot/3.png") no-repeat;
            background-size: contain;
        }
        30% {
            background: url("../images/football/shot/4.png") no-repeat;
            background-size: contain;
        }
        40% {
            background: url("../images/football/shot/5.png") no-repeat;
            background-size: contain;
        }
        50% {
            background: url("../images/football/shot/6.png") no-repeat;
            background-size: contain;
        }
        60% {
            background: url("../images/football/shot/7.png") no-repeat;
            background-size: contain;
        }
        70% {
            background: url("../images/football/shot/8.png") no-repeat;
            background-size: contain;
        }
        80% {
            background: url("../images/football/shot/9.png") 0 0 no-repeat;
            background-size: contain;
        }
        90% {
            background: url("../images/football/shot/10.png") 0 0 no-repeat;
            background-size: contain;
        }
        
    }
    .sprite {
        display: inline-block;
        width: 500px; /*px*/
        height: 100px; /*px*/
        background-size: contain;
        &.juggle {
            animation: runJuggle 0.6s infinite;
        }
        &.shot {
            animation: runShot 0.6s;
        }
    }
}
</style>
