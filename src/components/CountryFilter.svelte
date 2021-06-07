<script>
	let selectedCountry = '';

	const handleChange = (e) => {
		selectedCountry = e.target.value;
	};
</script>

<div class="filter">
	<div>
		<input name="full-time" type="checkbox" />
		<label for="full-time">Full time</label>
	</div>
	<input class="location-search" type="text" placeholder="City, state, zip code or country" />
	<div class="country-filter">
		<div>
			<input type="radio" on:change={handleChange} name="selected_country" value="London" /><span
				>London</span
			>
		</div>
		<div>
			<input type="radio" on:change={handleChange} name="selected_country" value="Amsterdan" /><span
				>Amsterdan</span
			>
		</div>
		<div>
			<input type="radio" on:change={handleChange} name="selected_country" value="New York" /><span
				>New York</span
			>
		</div>
		<div>
			<input type="radio" on:change={handleChange} name="selected_country" value="Berlin" /><span
				>Berlin</span
			>
		</div>
	</div>
</div>

<style lang="scss">
	.location-search {
		margin-top: 1rem;
		height: 3rem;
		padding-left: 1rem;
		padding-right: 1rem;
		border: none;
		box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.05);
		border-radius: 4px;
	}

	.filter {
		display: flex;
		flex: 0.25;
		flex-direction: column;
	}

	.country-filter {
		display: flex;
		flex-direction: column;
		margin-top: 1rem;

		div {
			margin-top: 0.5rem;

			span {
				margin-left: 0.5rem;
			}
		}
	}
</style>
