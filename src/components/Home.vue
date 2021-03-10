<template>
	<div class="home">
		<section id="intro">
			<div class="title-wrap">
				<img src="../assets/images/dog_cat.svg" alt="кошка и собака">
				<h1>{{ title }}<br>это <b><i>Лапка</i></b></h1>
			</div>
			<p>Сервис заботы для питомцев и их хозяев.
				<br>И вся клиника «Белый Клык»
				<br>в одном приложении
			</p>
		</section>
		<section></section>
		<section></section>
		<section></section>
		<section></section>
	</div>
</template>

<script>
export default {
	name: 'Home',
	computed: {
		title() {
			let now = new Date().getHours()
			if (now < 7) return 'Доброй ночи'
			if (now > 6 && now < 12) return 'Доброе утро'
			if (now > 11 && now < 18) return 'Добрый день'
			if (now > 7) return 'Добрый вечер'
		}
	}
	
}
</script>

<style lang="scss"  scoped>
section {
	height: 100vh;
	max-height: 945px;
	min-height: -webkit-fill-avaliable;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	padding: 0 20px;
	text-align: center;
}

#intro {
	.title-wrap {
		position: relative;
		height: 160px;
		margin-bottom: 20px;
		display: flex;

		&:before {
			content: '';
			position: absolute;
			top: 0;
			left: 0;
			right: 0;
			bottom: 0;
			    z-index: 1;
			background: linear-gradient(to top, #f4f4f4, rgba(#f4f4f4, 0));
		}
		@media (min-width: 375px) {
			height: 200px;
			margin-bottom: 30px;
		}
		@media (min-width: 720px) {
			height: 400px;
			margin-bottom: 60px;
		}
	}
	img, h1, p {
		opacity: 0;
		animation-name: fade-in;
		animation-duration: 1s;
		animation-fill-mode: forwards;
	}

	img {
		position: absolute;
		left: 0;
		right: 0;
		bottom: 0;
		margin: auto;
		width: 100%;
		max-width: 612px;
		animation-delay: 0s;
		z-index: 0;
	}
	h1 {
		position: relative;
		margin-top: auto;
		animation-delay: .4s;
		z-index: 1;
	}
	p {
		animation-delay: .8s;
	}
}

@keyframes fade-in {
	to {
		opacity: 1;
	}
}

h1, h2 {
	// font-family: 'NY', sans-serif;
}

h1 {
	font-size: 42px;
	line-height: 1;
	white-space: nowrap;

	@media (min-width: 375px) {
		font-size: 48px;
	}

	@media (min-width: 725px) {
		font-size: 80px;
	}
}

</style>
