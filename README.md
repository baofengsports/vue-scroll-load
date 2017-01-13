# 滚动刷新组件

> 上拉刷新、下拉刷新、自定义加载动画




## 使用方法



```html
<scroll-load ref="listScroll" class="list-scroll" :dropType="dropType" @loadMore="onListLoadMore" @loadMoreUp="onListLoadMoreUp">
	<div slot="content" ref="listWrap" class="list-wrap" >
		<!-- 你的内容 -->
	</div>
</scroll-load>

```

```javascript
	methods: {
		onListLoadMore() {
            ajax({url: 'xxx', params: {}}, (res) => { // ajax 请求 伪代码
	            // 塞数据
	            for (var key in res) {
	                this.data.push(res[key]);
	            }

	            if(res.length === 0) { // 通知组件没有更多数据了
            		this.listScroll.noMore()
	            } else {
	            	this.$nextTick(() => { // dom更新之后再通知组件加载完毕
		            	this.listScroll.loadFinished()
		            })
	            }
	        })
		},
		onListLoadMoreUp() {
			if(this.scheduleList.length === 0) {
				this.busy = false;
				return;
			};
            ajax({url: 'xxx', params: {}}, (res) => { // ajax 请求 伪代码
	            for (var key in res) {
	                this.data.push(res[key]);
	            }

            	this.$nextTick(() => {
            		this.listScroll.loadFinished()
	            	
	            })
	        })
		},
```

## 使用条件
这个组件必须要有滚动条才可以

## 自定义动画
组件默认提供了`normal`、`basketball`、`football`三种加载动画，也可以自己定义动画，如例子中通过slot将内容分发到组件中

```html
<scroll-load class="list-scroll" :dropType="dropType" @loadMore="onListLoadMore" @loadMoreUp="onListLoadMoreUp">
	<div slot="drop"><!-- 你的自定义的加载动画 --></div>
	<div slot="content" ref="listWrap" class="list-wrap" >
		<!-- 你的内容 -->
	</div>
</scroll-load>

```

## 参数


参数 | 说明 | 类型 | 可选值 | 默认值
------- | ------- | ------- | ------- | -------
dropType | 下拉动画 | String | 'normal'/'basketball'/'football'  | 'normal'

## 事件
参数 | 说明 | 
------- | ------- |
loadMoreUp | 下拉刷新触发的事件 | 
loadMore | 上拉刷新触发的事件 | 


## 例子

<p align="center">
  <br>
  <img width="400" src="https://rawgit.com/baofengsports/vue-scroll-load/master/demo.png" alt="awesome">
  <br>
  <br>
</p>
