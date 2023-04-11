<script>
	import { goto } 		from "@sapper/app"
	import { likeCount } 	from "../store/store";

	export let segment;

	const navigateHome = async () => {
		await goto("/");
	};

</script>

<div class="Header">
	<div class="Header-container">
		<div class="Header-content">
			<div class="Header-logo">

				<img
					src			= "https://res.cloudinary.com/dbgzsikcs/image/upload/v1680893663/instapetsgram/WhatsApp_Image_2023-04-07_at_2.47.58_PM-removebg-preview_dn45ww.png"
					alt			= "logo"
					width		= "250"
					height		= "70"
					on:click	= { navigateHome }
					on:keypress	= { navigateHome }
				>

			</div>

			<div class="Header-nav">
				<ul>
					<li>
						<i class="fas fa-heart" />

						{ $likeCount === 0 ? '' : $likeCount }

					</li>

					<li>
						<a
							href			= "profile"
							rel				= "prefetch"
							aria-current	= { segment === 'profile' ? 'page' : undefined }
						>
							<i class="fas fa-user-alt"/>
						</a>
					</li>
				</ul>
			</div>
		</div>
	</div>
</div>

<style>
	.Header {
		background-color: white;
		position: fixed;
		width: 100%;
	}

	.Header-container {
		grid-template-columns: minmax(auto, 936px);
		display: grid;
		justify-content: center;
		background-color: white;
		border-bottom: 1px solid rgba(38, 38, 38, 0.4);
	}

	.Header-content {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 0.5em;
	}

	.Header ul {
		list-style: none;
	}

	.Header li {
		display: inline-block;
		margin: 0 0 0 1em;
	}

	.Header i {
		font-size: 16px;
		color: rgba(38, 38, 38, 0.7);
		cursor: pointer;
	}

	[aria-current] i {
		color: #bc1888;
	}
</style>
