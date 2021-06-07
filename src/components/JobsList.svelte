<script>
	import JobCard from './JobCard.svelte';

	let skip = 0;

	export let jobs;
</script>

<div class="jobs">
	{#each jobs.slice(skip, skip + 9) as job}
		<JobCard {job} />
	{/each}
	<div class="pagination">
		<button
			disabled={skip === 0 || skip - 9 <= 0}
			on:click={() => {
				skip = skip - 9;
				window.scrollTo(0, 0);
			}}
			><svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-6 w-6"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
			>
				<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
			</svg></button
		>
		<button
			on:click={() => (skip = skip + 9)}
			disabled={skip === jobs.length || skip + 9 >= jobs.length}
			><svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-6 w-6"
				fill="none"
				viewBox="0 0 24 24"
				stroke="currentColor"
			>
				<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
			</svg></button
		>
	</div>
</div>

<style lang="scss">
	.jobs {
		flex: 0.75;
		padding-left: 1.5rem;

		.pagination {
			display: flex;
			justify-content: flex-end;
			margin-bottom: 2.5rem;

			button {
				background-color: #f6f7fb;
				border: 1px solid #b7bcce;
				box-sizing: border-box;
				border-radius: 4px;
				padding: 0.5rem;

				svg {
					width: 20px;
					height: 20px;
					color: #b7bcce;
				}

				&:first-child {
					margin-right: 1.5rem;
				}

				&:hover:enabled {
					cursor: pointer;
					background-color: #1e86ff;

					svg {
						color: white;
					}
				}
			}
		}
	}
</style>
