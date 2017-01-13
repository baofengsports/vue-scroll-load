<template>
<!-- 滚动刷新 开始 -->
<div class="scroll-load" @touchstart="onTouchStart" @touchmove="onTouchMove" @touchend="onTouchEnd" @scroll="onScroll">
    <slot v-if="$slots.drop" name="drop" ref="dropUpdate"></slot>
    <normal-drop v-else-if="dropType === 'normal'" ref="dropUpdate"></normal-drop>
    <basketball-drop v-else-if="dropType === 'basketball'" ref="dropUpdate"></basketball-drop>
    <football-drop v-else-if="dropType === 'football'" ref="dropUpdate"></football-drop>

    <slot name="content"></slot>
    <div class="push-update" >
        <loading class="loading"></loading>
        <span>{{ loadText }}</span>
    </div>
</div>
<!-- 滚动刷新 结束 -->
</template>

<script>
import NormalDrop from './normalDrop.vue'
import BasketballDrop from './basketballDrop.vue'
import FootBalllDrop from './footballDrop.vue'
import Loading from '../../loading/src/main.vue'

export default {
	name : 'button',
    components: {
        Loading, NormalDrop, BasketballDrop, FootBalllDrop
    },
    mounted() {
        this.dropUpdate = this.$refs.dropUpdate;
        this.dropHeight = this.dropUpdate.$el.offsetHeight;
    },
	props : {
        // 下拉刷新动画，‘normal’－一般样式，‘basketball’－打篮球
        dropType: {
            type: String,
            default: 'normal'
        },
	},
	data () {
		return {
            busy: false, // 是否正在加载数据,
            loadText: '加载中...',
            dropHeight: 0
		}
	},
    computed: {

        
    },
	methods : {
        onTouchStart(event) {
            if(this.$el.scrollTop !== 0) return ;
            // 下拉
            let touch = event.targetTouches[0];
            this.lastTouchPosY = touch.clientY
        },
        onTouchMove(event) {
            // 下拉
            if(this.$el.scrollTop !== 0) return ;
            let touch = event.targetTouches[0];
            let mt = -(this.dropHeight - (touch.clientY - this.lastTouchPosY)/2);

            this.dropUpdate.$el.style.marginTop = mt + 'px';
            if(mt >= -2) {
                this.dropUpdate.dropState = 'release'
            }
        },
        onTouchEnd() {
            if(this.$el.scrollTop !== 0) return;
            // 下拉
            let mt = this.dropUpdate.$el.style.marginTop;

            if(parseInt(mt.substring(0, mt.length-2)) > -2) {
                this.dropUpdate.dropState = 'update'
                if(!this.busy) {
                    this.$emit('loadMoreUp');
                    this.busy = true;
                }
            } else {
                this.dropUpdate.$el.style.marginTop = -this.dropHeight + 'px';
            }
        },
        onScroll() {
            if(this.$el.scrollHeight <= (this.$el.clientHeight + this.$el.scrollTop + this.dropHeight) ) {
                // 上拉
                if(!this.busy) {
                    this.$emit('loadMore');
                    this.busy = true;
                }
            } 
        },
        loadFinished() {
            this.busy = false;
            if(this.isPushing) return;
            this.dropUpdate.dropState = 'complete'
            this.dropUpdate.$el.style.transition = 'all 1s'
            this.dropUpdate.$el.style.marginTop = -this.dropHeight + 'px';
            
            setTimeout(() => {
                this.dropUpdate.$el.style.transition = ''
                this.dropUpdate.dropState = 'drop'
            }, 1000)
        },
        noMore() {
            this.loadText = '没有更多数据了～'
        }
	}
}
</script>

<style lang="scss" scoped>
.scroll-load {
    
    .push-update {
        height: 100px;  /*px*/
        line-height: 100px; /*px*/
        text-align: center;
        font-size: 24px; /*px*/
        background: #f1f1f1;

        .loading {
            display: inline-block;
            top: 12px; /*px*/
            margin-right: 10px; /*px*/
        }
    }
}

</style>
