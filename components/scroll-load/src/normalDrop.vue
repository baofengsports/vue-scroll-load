<template>
	<div class="drop-update" >
        <loading v-show="dropState === 'update'" class="loading"></loading>
        <div v-show="dropState === 'drop'">下拉刷新</div>
        <div v-show="dropState === 'release'">释放更新</div>
    </div>
</template>
<script>
import Loading from '../../loading/src/main.vue'

export default {
	components: {
        Loading
    },
	data () {
		return {
            dropState: 'drop', // 下拉时的状态，‘drop’－正在下拉， ‘release’－手指释放， ‘update’－正在更新数据，‘complete’－‘数据更新成功’
		}
	},
}
</script>
<style lang="scss">
.drop-update {
    margin-top: -100px; /*px*/
    height: 100px;  /*px*/
    line-height: 100px; /*px*/
    background: #f1f1f1;
    text-align: center;
    font-size: 24px; /*px*/

    .loading {
        display: inline-block;
    }
}
</style>