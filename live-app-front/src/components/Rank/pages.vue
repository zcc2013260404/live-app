<template>
		<div class="Ra-pages">
		<div v-if="data">
			<img :src="data[0].userimage" @click="goDetail">
			<img :src="data[1].userimage" @click="goDetail">
			<img :src="data[2].userimage" @click="goDetail">
			<svg class="icon" aria-hidden="true">
			  <use xlink:href="#iconhuangguan" ></use>
			</svg>
			<svg class="icon" aria-hidden="true">
			  <use xlink:href="#iconliubianxing_tianchong" ></use>
			</svg>
			<svg class="icon" aria-hidden="true">
			  <use xlink:href="#iconliubianxing_tianchong" ></use>
			</svg>
			<i>2</i>
			<i>3</i>
			<div v-for="(n,index) in data.slice(0,3)">
				<h1>{{n.userid}}</h1>
				<span></span>
				<h2>魅力值：{{n.charsma}}</h2>
			</div>
		</div>
		<div class="list">
			<div v-for="(n,index) in data.slice(3,data.length)" @click="goDetail">
				<h3>
					<p>{{index+4}}</p>
					<img :src="n.userimage">
					<h1>{{n.userid}}</h1>
					<span></span>
				</h3>
				<h2>魅力值：{{n.charsma}}</h2>
			</div>
		</div>
	</div>
	</template>

<script>
  export default {
    name: 'Star',
	props: ['data'],
	methods:{
		goDetail(){
			this.$router.push("/user/fans");
		}
	}
  }
</script>
<style lang="scss">
	.Ra-pages{
    overflow-x: hidden;
    width: 100vw;
		height: 5.6rem;
		margin-top: 0.1rem;
		display: flex;
		flex: 1;
		overflow-y: auto;
		flex-wrap: wrap;
		>div{
			width: 100%;
		}
		>div:first-child{
			height: 2.45rem;
			background: url(http://122.51.57.152:4000/images/bg2.jpg);
			background-size: 100% 100%;
			img{
				width: 0.67rem;
				height: 0.67rem;
				border: 0.04rem solid #fff;
				border-radius: 50%;
				position: relative;
				&:nth-of-type(1){
					width: 0.86rem;
					height: 0.86rem;
					top: 0.6rem;
					left: 1.45rem;
				}
				&:nth-of-type(2){
					top: 0.8rem;
					left: -0.8rem;
				}
				&:nth-of-type(3){
					top: 0.8rem;
					left: 1.1rem;
				}
			}
			svg{
				width: 0.37rem;
				height: 0.37rem;
				fill: gold;
				position: relative;
				&:nth-of-type(1){
					top: -0.22rem;
					left: -0.7rem;
				}
				&:nth-of-type(2){
					fill: #29bff5;
					top: 0.38rem;
					left: -2.7rem;
				}
				&:nth-of-type(3){
					fill: #ffa94e;
					top: 0.38rem;
					left: -0.5rem;
				}
			}
			i{
				font-size: 0.18rem;
				font-weight: bolder;
				color: rgba(#fff,0.9);
				position: relative;
				display: inline-block;
				transform: rotate(20deg);
				&:nth-of-type(1){
					top: 0.25rem;
					left: -3.32rem;
				}
				&:nth-of-type(2){
					top: 0.073rem;
					left: 2.8rem;
				}
			}
			div{
				color: #fff;
				position: relative;
				h1{
					font-size: 0.12rem;
					margin-bottom: 0.1rem;
				}
				span{
					margin-bottom: 0.12rem;
				}
				&:nth-of-type(1){
					top: 0.65rem;
					left: 1.3rem;
				}
				&:nth-of-type(2){
					top: 0.35rem;
					left: 0.06rem;
				}
				&:nth-of-type(3){
					top: -0.1rem;
					left: 2.65rem;
				}
			}
		}
	}
	.Ra-pages{
		span{
			display: inline-block;
			width: 0.32rem;
			height: 0.17rem;
			background:url(http://122.51.57.152:4000/images/vip.png) no-repeat;
			background-size: 0.14rem;
			margin-left: 0.05rem;
		}
		h1{
			display: inline-block;
			max-width: 0.58rem;
			font-size: 0.15rem;
			height: 0.15rem;
			overflow: hidden;
			text-overflow:ellipsis;
			white-space:nowrap;
		}
		.list{
			background-color: #fff;
			min-height: 3.15rem;
			>div{
				display: flex;
				justify-content: space-between;
				align-items: center;
				padding: 0.15rem 0rem 0.15rem 0.11rem;
				margin: 0rem 0.1rem;
				h3{
					display:flex;
					align-items: center;
					>*{
						margin-right: 0.1rem;
					}
					p{
						color: #ababab;
					}
					img{
						width: 0.53rem;
						height: 0.53rem;
						border-radius: 50%;
					}
				}
				h2{
					color: #959593;
					font-size: 0.13rem;
				}
			}
		}
	}

</style>