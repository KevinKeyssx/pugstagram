<script>
	export let comments = [];

	function addComment( event ) {

		const msg = event.target.text.value;

		if ( msg.length > 3 ) {

			const message = {
				id		: Date.now(),
				text	: msg,
				username: 'Crispy'
			}

			comments = [ ...comments, message ];
			event.target.text.value = '';

		}

	}
</script>

<div class="Comment">

	<div class="Comment-content">

		{#each comments as comment}
			<div class="Comment-users">
				<h3>{comment.username}</h3>
				<span>{comment.text}</span>
			</div>
		{/each}

		<div class="Comment-add">
			<form on:submit|preventDefault={addComment}>
				<input
					type		= "text"
					class		= "Comment-input"
					name		= "comment"
					id			= "text"
					placeholder	= "Agrega un comentario..."
				/>

				<button
					type	= "submit"
					class	= "Comment-button"
				>
					<i class="fas fa-paper-plane" />
				</button>
			</form>
		</div>
	</div>


</div>

<style>
	.Comment h3 {
		font-size: 14px;
		color: black;
		font-weight: bold;
		margin: 0;
		padding: 0;
	}
	.Comment span {
		font-size: 14px;
		margin: 0 0 0 0.5em;
		font-weight: normal;
		color: rgba(black, 0.9);
	}
	.Comment-add {
		padding: 1em 1em 1em 1em;
		border-top: 1px solid rgba(219, 219, 219, 0.8);
	}
	.Comment-add form {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.Comment-content {
		padding: 0 1em 0.5em 1em;
	}
	.Comment-users {
		margin: 0 0 0.5em 0;
		display: flex;
	}

	input {
		border: solid 1px #e9e9e9;
		border-radius: 5px;
		color: #696969;
		border: 1px solid transparent;
		font-size: 12px;
		outline: none;
		width: 100%;
		display: flex;
	}
	button {
		border: none;
		color: #3897f0;
		font-size: 12px;
		outline: none;
		cursor: pointer;
	}

</style>
