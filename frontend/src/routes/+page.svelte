<script lang="ts">
	const subTitle = 'Zenn is good service!!';
	let tasks: string[] = [];

	async function getSomething() {
		fetch('http://localhost:3000/api/v1/tasks')
			.then((response) => response.json())
			.then((data) => {
				tasks = data.tasks;
			});
	}
</script>

<div class="container">
	<div>
		<h1 class="title">Zenn-app</h1>
		<h2 class="subtitle">
			{subTitle}
		</h2>
		<button on:click={getSomething}> タスク取得 </button>
		<ul>
			{#each tasks as task}
				<li>{task.title}</li>
			{/each}
		</ul>
	</div>
</div>
