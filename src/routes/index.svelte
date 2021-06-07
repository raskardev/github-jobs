<script context="module">
	export async function load({ fetch }) {
		const res = await fetch('https://jobs.github.com/positions.json');

		if (res.ok) {
			return {
				props: {
					jobs: await res.json()
				}
			};
		}

		return {
			status: res.status,
			error: new Error(`Could not fetch positions`)
		};
	}
</script>

<script>
	import CountryFilter from '../components/CountryFilter.svelte';
	import JobsList from '../components/JobsList.svelte';
	import Search from '../components/Search.svelte';

	export let jobs;
</script>

<Search />
<div class="container">
	<CountryFilter />
	<JobsList {jobs} />
</div>

<style lang="scss">
	.container {
		display: flex;
		margin-top: 1.5rem;
	}
</style>
