<script>
	export let data;
  import { base } from '$app/paths';
</script>
<main>
	<br>
	<br>

<h1>Devblog</h1>

<ul>
	{#each data.posts as post}
		<li>
			<a href="{base}/devblog/{post.slug}">
				{post.title} — {post.date}
			</a>
		</li>
	{/each}
</ul>

</main>


<style>
main{
		width: 100vw;
		height: 100vh;
		background-color: black;
	}

	
</style>
