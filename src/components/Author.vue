<template>
	<div class="author">

		<g-image alt="Author image" class="author__image" src="~/assets/images/author.jpg" width="180" height="180" blur="5" />

		<h1 v-if="showTitle" class="author__site-title">
			{{ $static.metaData.siteName }}
		</h1>

		<p class="author__intro">
			Boletines y notas de prensa del Museo Municipal de Guayaquil.
		</p>

		<p v-if="showLinks" class="author__links">
			<a href="//museoarteyciudad.com">Museo Arte y Ciudad</a>
			<a href="//www.facebook.com/MUMG-Museo-Municipal-de-Guayaquil-68122309693/">Facebook</a>
		</p>

	</div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<script>
export default {
	props: ['showTitle', 'showLinks']
}
</script>

<style lang="scss">
.author {
	margin: 0 auto;
	max-width: 500px;
	text-align: center;
	padding: calc(var(--space) / 2) 0;

	&__image {
		border-radius: 100%;
		width: 90px;
		height: 90px;
		margin-bottom: 1em;
	}

	&__intro {
		opacity: .8;
	}

	&__site-title {
		font-size: 1.5em;
		font-family: "Impact", sans-serif;
	}

	&__links {
		margin-top: -.5em;
		a {
			margin: 0 .5em;
		}
	}
}
</style>
