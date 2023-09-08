<template>
	<div class="menu-container">
		<div class="box" :class="{ 'box-visible': boxVisible }">
			<div class="container">
				<div class="service-title">Spa Pedicure</div>
				<div class="row" v-for="(pedSevice, index) in pedSevices" :key="index">
					<div class="col-8 text-start">
						{{ pedSevice.name }}
					</div>
					<div class="col-4 text-end">{{ pedSevice.price }}</div>
				</div>

				<div class="service-title">Manicure</div>
				<div class="row" v-for="(manicureSevice, index) in manicureSevices" :key="index">
					<div class="col-8 text-start">{{ manicureSevice.name }}</div>
					<div class="col-4 text-end">{{ manicureSevice.price }}</div>
				</div>

				<div class="service-title">Dipping Powder</div>
				<div class="row" v-for="(dipSevice, index) in dipSevices" :key="index">
					<div class="col-8 text-start">{{ dipSevice.name }}</div>
					<div class="col-4 text-end">{{ dipSevice.price }}</div>
				</div>
				<div class="row">
					<div class="col-8 text-start">
						Coffin/Almond Shape
						<i
							class="fa fa-solid fa-circle-question"
							type="button"
							data-bs-toggle="modal"
							data-bs-target="#exampleModal"
						></i>
					</div>
					<div class="col-4 text-end">+$5 & Up</div>
				</div>

				<div class="service-title">Arcylic</div>
				<div class="row" v-for="(acrylicSevice, index) in acrylicSevices" :key="index">
					<div class="col-8 text-start">{{ acrylicSevice.name }}</div>
					<div class="col-4 text-end">{{ acrylicSevice.price }}</div>
				</div>
			</div>
			<div class="mt-3 mb-2">
				<div style="font-size: 13px">*Credit card: 3% Convenience Fees</div>
			</div>
		</div>

		<!-- Modal content here  -->
		<div
			class="modal fade"
			id="exampleModal"
			tabindex="-1"
			aria-labelledby="exampleModalLabel"
			aria-hidden="true"
		>
			<div class="modal-dialog modal-dialog-centered">
				<div class="modal-content shape-color">
					<div class="modal-header shape-content">
						<button
							type="button"
							class="btn-close"
							data-bs-dismiss="modal"
							aria-label="Close"
						></button>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				pedSevices: [
					{ name: 'Regular Polish', price: '$27 & Up' },
					{ name: 'Gel Polish', price: '$40 & Up' },
					{ name: 'Delux Pedicure', price: '$40 & Up' },
					{ name: 'Pampering (Delux w/ Gel)', price: '$55 & Up' },
				],
				manicureSevices: [
					{ name: 'Regular', price: '$20 & Up' },
					{ name: 'Gel Polish', price: '$33 & Up' },
				],
				dipSevices: [
					{ name: 'Real Nails', price: '$35 & Up' },
					{ name: 'Extended Tip', price: '$40 & Up' },
					{ name: 'French Tip', price: '$45 & Up' },
					{ name: 'Dips w/ Manicure', price: '$50 & Up' },
					// { name: 'Coffin or Almond Shape', price: '+$5 & Up' },
				],
				acrylicSevices: [
					{ name: 'Full Set', price: '$35 & Up' },
					{ name: 'Full Set w/ Gel', price: '$45 & Up' },
					{ name: 'Full Set On Toes', price: '$25 & Up' },
					{ name: 'Full Set Pink & White', price: '$45 & Up' },
				],
				boxVisible: false,
			};
		},
		mounted() {
			window.addEventListener('scroll', this.handleScroll);
		},
		methods: {
			handleScroll() {
				const scrollPosition = window.scrollY;
				const viewportHeight = window.innerHeight;
				const triggerPoint = viewportHeight * 0.5; // 50vh

				if (scrollPosition >= triggerPoint) {
					this.boxVisible = true;
					// Remove the scroll event listener once the elements are visible (optional)
					window.removeEventListener('scroll', this.handleScroll);
				}
			},
		},
	};
</script>

<style>
	.menu-container {
		height: 100vh;
		min-height: 650px;
		width: 100%;
		background-image: url('../assets/bg3.jpg');
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
		background-position-y: center;
		position: relative;
		overflow: hidden;
	}
	.box {
		border: 2px solid #fff;
		background-color: rgba(255, 255, 255, 0.1);
		border-radius: 15px;
		width: 85%;
		max-width: 650px;
		height: 85%;
		min-height: 600px;
		overflow: hidden;
		overflow-y: auto;

		font-family: 'Tenor Sans', sans-serif;
		color: #fff;

		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;

		position: absolute;
		top: 50%;
		left: 50%;
		/* transform: translate(-50%, -50%); */

		transform: translate(30%, -50%); /* Initially, move the element 100% to the right, off-screen */
		opacity: 0; /* Initially, hide the element */
	}

	.box-visible {
		transform: translate(-50%, -50%);
		opacity: 1;
		transition: transform 1s ease-out, opacity 2.3s ease-out;
	}
	.service-title {
		font-family: 'Garet', sans-serif;
		text-transform: uppercase;
		margin-top: 12px;
		font-size: 20px;
		text-decoration: 0.5px underline;
	}

	.shape-content {
		height: 50vh;
		width: 90%;
		margin: auto;
		justify-content: center;
		align-items: baseline;
		background-image: url('../assets/shape.PNG');
		background-size: contain;
		background-repeat: no-repeat;
		background-position: center;
	}
	.shape-color {
		background-color: #fcf1f0;
	}
</style>
