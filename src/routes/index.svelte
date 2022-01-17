<script context="module" lang="ts">
	export const prerender = true;

	const getMovies = `// groq     
 {
     'movies': *[_type == "movie"] | order(_createdAt desc) [0..4]
      {
        title,
        poster{asset->{path,url}},
        'cast': {'name': castMembers[0].person->name, 
                 'Character': castMembers[0].characterName}
      }
  }
`;

	export async function load({ params }) {}
</script>

<script lang="ts">
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<div>
	<h1>Pizza Time</h1>
</div>

<style>
	div {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}
</style>
