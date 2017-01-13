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
    $height: 150px;
    margin-top: -$height;
    width: 750px;
    height: $height;
    line-height: $height;
    background: #f1f1f1;
    text-align: center;
    font-size: 24px; /*px*/
    
    .sprite {
        display: inline-block;
        width: 100%; /*px*/
        height: 100%; /*px*/
        
        &.juggle {
            background: url("../images/basketball/juggle.gif") 0 0 no-repeat;
            background-size: contain;
        }
        &.shot {
            background: url("../images/basketball/shot.gif") 0 0 no-repeat;
            background-size: contain;
        }
    }
}
</style>
