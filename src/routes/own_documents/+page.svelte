<script lang="ts">
	import { getCurrentModel } from '$lib/local_store';

	async function getModelName() {
		getCurrentModel().then((currenModel) => {
			if (currenModel) {
				console.log(currenModel.name);
				modelName = currenModel.name;
			}
		});
	}
	getModelName();
	let modelName: string;
</script>

<div class="h-screen flex flex-col">
	<div class="p-4">
		<h2>Query your documents</h2>
		<div class="flex items-center">
			{#if modelName != null}
				<p class="text-xl text-warning-400">{modelName}</p>
			{:else}
				<p class="text-xl text-error-500">No active model</p>
			{/if}
		</div>
	</div>
	<div class="flex justify-center items-center h-full">
		<h3 class="mt-3">Coming soon... 🚀</h3>
	</div>
</div>
