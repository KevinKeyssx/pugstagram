<script>
	export let nickname;
	export let name;
</script>

<div class="Profile">
	<a
		href="profile"
		rel="prefetch"
	>

		<div class="Profile-content">
			<div class="Profile-avatar">
				<img src="https://placekitten.com/200/200" alt="avatar" />
			</div>
			<div class="Profile-info">
				<h2>{nickname}</h2>
				<span>{name}</span>
			</div>
		</div>
	</a>
</div>

<style>
	.Profile-content {
		display: flex;
		align-items: center;
	}
	.Profile-avatar img {
		width: 42px;
		height: 42px;
		border-radius: 50%;
	}
	.Profile-info {
		margin: 0 0 0 0.5em;
	}
	.Profile-info h2 {
		font-size: 14px;
		color: black;
		margin: 0;
		padding: 0;
	}
	.Profile-info span {
		font-size: 12px;
		font-weight: normal;
	}

	a {
		text-decoration: none;
	}
</style>
