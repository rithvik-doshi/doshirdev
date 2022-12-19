<script>
	import Counter from './Counter.svelte';
	// import welcome from '$lib/images/svelte-welcome.webp';
	import da_pic from '$lib/images/Snow3.jpeg';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="The home of all things Rithvik" />
</svelte:head>

<section>
	<h1>
		<div><img id="da_pic" src={da_pic} alt="Welcome" /></div>
		Hey there!
		<br>
		I'm Rithvik :D
	</h1>

	<h2>
		This is a cool website. I think. I hope so
	</h2>

	<!-- <Counter /> -->

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

	#da_pic{
			width: 50%;
			height: 50%;
			border-radius: 2%;
	}
	
</style>
