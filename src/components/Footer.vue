<template>
	<div class="footer-1">
		<div>
			<ul>
				<li>Mon-Fri: 10AM - 7PM</li>
				<li>Sat: 9:30AM - 7PM</li>
				<li>Sun: Closed</li>
			</ul>
		</div>

		<div class="info-2 info-3"><a :href="'tel:' + 8172223869">(817) 222-3869</a></div>
		<div class="text-ft">
			<i class="fa fa-solid fa-location-dot icon"></i>5500 Broadway Ave, Haltom City, TX 76117
		</div>
	</div>
</template>

<script></script>

<style>
	.footer-1 {
		width: 100%;
		height: 35vh;
		background-image: url('../assets/background.png');
		/* background-image: url('../assets/footer.PNG'); */
		background-position: bottom;
		background-repeat: no-repeat;
		background-size: cover;
		color: #000;
		display: flex;
		text-align: center;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		font-size: 13px;
	}
	ul {
		padding: 0;
		margin: 0;
	}
	li {
		list-style-type: none;
		font-family: 'Garet', sans-serif;
		letter-spacing: 1px;
		font-weight: bold;
		font-size: 14px;
		text-transform: capitalize;
	}
	.icon {
		margin-right: 10px;
	}
	.info-3 {
		margin: 10px;
		padding: 5px 20px;
	}
	.text-ft {
		font-family: 'Garet', sans-serif;
		letter-spacing: 1px;
		font-weight: 700;
		font-size: 13px;
		margin-top: 5px;
	}
</style>
