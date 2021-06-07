<script>
	import { dateFromNow } from '../lib/day';

	export let job;
</script>

<div class="card">
	{#if job.company_logo}
		<div class="logo" style="background-image: url({job.company_logo});" />
	{/if}
	<div class="job-info">
		<p class="company-title">{job.company}</p>
		<h1 class="job-title">{job.title}</h1>
		<div class="extra-info">
			{#if job.type === 'Full Time'}
				<div class="full-time"><span>Full time</span></div>
			{/if}
			<div class="time-info">
				<div class="location">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-6 w-6"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M3.055 11H5a2 2 0 012 2v1a2 2 0 002 2 2 2 0 012 2v2.945M8 3.935V5.5A2.5 2.5 0 0010.5 8h.5a2 2 0 012 2 2 2 0 104 0 2 2 0 012-2h1.064M15 20.488V18a2 2 0 012-2h3.064M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
						/>
					</svg>
					<span> {job.location}</span>
				</div>
				<span>{dateFromNow(job.created_at)}</span>
			</div>
		</div>
	</div>
</div>

<style lang="scss">
	.card {
		display: flex;
		flex-direction: row;
		align-items: center;
		margin-bottom: 2rem;
		padding: 1rem 1.5rem;
		background: #ffffff;
		box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.05);
		border-radius: 4px;

		.logo {
			display: flex;
			margin-right: 1rem;
			width: 120px;
			height: 110px;
			background-size: cover;
			background-position: center center;
			border-radius: 4px;
		}

		.job-info {
			display: flex;
			flex-direction: column;
			width: 100%;
		}

		.extra-info {
			display: flex;
			justify-content: space-between;
			align-items: center;
			height: 26px;

			span {
				font-size: 14px;
				font-weight: bold;
				color: #334680;
			}

			.full-time {
				width: 80px;
				border: 1px solid #334680;
				box-sizing: border-box;
				border-radius: 4px;
				padding: 0 0.5rem;
			}

			.time-info {
				display: flex;
				flex: 0.3;
				justify-content: space-between;

				span {
					color: #b9bdcf;
					font-size: 14px;
					font-weight: normal;
				}

				.location {
					display: flex;
					svg {
						color: #b9bdcf;
						width: 20px;
						height: 20px;
						margin-right: 5px;
					}
				}
			}
		}

		.company-title {
			font-weight: bold;
			color: #334680;
			font-size: 16px;
			margin: 0;
		}

		.job-title {
			color: #334680;
			font-size: 24px;
			font-weight: normal;
			margin-top: 5px;
			margin-bottom: 10px;
		}
	}
</style>
