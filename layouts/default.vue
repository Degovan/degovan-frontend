<template>
	<div>
		<Nav />
		<div id="app">
			<Container>
				<Nuxt />
			</Container>
		</div>
		<Footer />
	</div>
</template>

<script>
import Nav from '~/components/layouts/Nav';
import Footer from '~/components/layouts/Footer';
import Container from '~/components/reusable/Container';

export default {
	components: {
		Nav, Footer, Container
	}	
}
</script>

<style lang="scss" scoped>
	#app {
		margin-top: 15vh;
		overflow: hidden;
	}
</style>