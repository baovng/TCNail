<template>
	<div class="container-wrp">
		<div class="txt-header" :class="{ appear: appear }">
			Promo
			<div class="txt-discount">{{ discount }} <span class="percent">10%</span></div>
		</div>
		<div class="info" :class="{ appear: appear2 }">
			T&C NAILS
			<div class="info-1">book now</div>
			<div class="info-2"><a :href="'tel:' + 8172223869">(817) 222-3869</a></div>
		</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				discount: 'Cash Discount',

				appear: false,
				appear2: false,
			};
		},
		mounted() {
			setTimeout(() => {
				this.appear = true;
			}, 300);
			setTimeout(() => {
				this.appear2 = true;
			}, 900);
		},
	};
</script>
<style>
	.container-wrp {
		/* background-color: peachpuff; */
		position: relative;
		background-image: url('../assets/background.png');
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
		background-position-y: center;
		width: 100%;
		height: 100vh;
		min-height: 450px;
		justify-content: center;
		align-items: center;
		display: flex;
		flex-direction: column;
	}

	.txt-header {
		font-family: 'Brittany', sans-serif;
		font-weight: 500;
		font-size: 100px;
		margin-top: -70px;
		color: #fff;
		opacity: 0;
	}
	.txt-discount {
		font-family: 'Garet', sans-serif;
		font-size: 18px;
		font-weight: bold;
		letter-spacing: 1px;
		text-transform: uppercase;
		margin-top: -60px;
		margin-left: 60px;
	}
	.percent {
		font-size: 30px;
		font-weight: bold;
	}
	.info {
		position: absolute;
		bottom: 6%;
		font-family: 'Commodus-Regular', sans-serif;
		font-size: 35px;
		letter-spacing: 1px;
		color: black;
		opacity: 0;
	}
	.info-1,
	.info-2 {
		font-family: 'Garet', sans-serif;
		font-size: 15px;
		text-transform: uppercase;
	}
	.info-2 {
		background-color: #8a4f31;
		color: #fff;
		padding: 5px 0px;
		margin-top: 5px;
	}
	a {
		text-decoration: none;
		color: #fff;
	}
	.appear {
		opacity: 1;
		transition: opacity 1s ease-in-out;
	}
</style>
