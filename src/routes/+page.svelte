<script>
	import Counter from './Counter.svelte';
	import Article from '../lib/Article.svelte';
	//import MyCounter from './MyCounter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';

	let posts = ['first post!', 'note to self: don\'t forget to do the dishes', 'another post']
	let newPost = '';

	function addPost() {
		posts = [...posts,newPost];
	}
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1>Home</h1>
	<!--
	<label>Talk to yourself: <input type="text" bind:value={newPost}></label>
	<button on:click={addPost}>Post it!</button>
	<div>
		{#each posts as post}
			<div>{post}</div>	
		{/each}
	</div>

	-->

	<Article
		blogTitle="Sandwiches are Great"
		blogBody="I just had the best sandwich."
		published = {true}/>

	<Counter />


	<!--
	<h1>
		<span class="welcome">
			<picture>
				<source srcset={welcome} type="image/webp" />
				<img src={welcome_fallback} alt="Welcome" />
			</picture>
		</span>

		to your new<br />SvelteKit app
	</h1>

	<h2>
		try editing <strong>src/routes/+page.svelte</strong>
	</h2>
	-->
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
