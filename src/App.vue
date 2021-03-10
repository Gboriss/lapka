<template>
	<div id="app">
		<Home />
	</div>
</template>

<script>
import Home from '@/components/Home'

export default {
	name: 'App',
	components: {
		Home
	}
}
</script>

<style lang="scss">
@import './styles/reset';
@import './styles/fonts';

#app {
	// font-family: SF,sans-serif;
    background-color: #f4f4f4;
}
</style>
