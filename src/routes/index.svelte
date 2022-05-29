<script>
	import {
		Content,
		Grid,
		Row,
		Column,
		Button,
		Modal,
		TextInput,
	} from "carbon-components-svelte";
	import "carbon-components-svelte/css/white.css";
	import Hidden from '../lib/modal/Hindden.svelte'
	let open = false;
	let show;
	let shown;
</script>

<Content>
	<Grid fullWidth padding>
		<Row>
			<h1>All stocks</h1>
			<Button on:click={() => (open = true)}>New stock</Button>

			<Modal
				bind:open
				modalHeading="New stock"
				primaryButtonText="Confirm"
				secondaryButtonText="Cancel"
				on:click:button--secondary={() => (open = false)}
				on:open
				on:close
				on:submit
			>
				<Grid padding>
					<Column>
						<TextInput labelText="Enter a stock to track" />
						<Button on:click={show}>Show advanced options</Button>
						<Hidden bind:shown bind:show>
							<h4>Hidden content</h4>
							<TextInput labelText="Enter a stock to track" />
							<TextInput labelText="Enter a stock to track" />
							<TextInput labelText="Enter a stock to track" />
							<TextInput labelText="Enter a stock to track" />
							<TextInput labelText="Enter a stock to track" />
							<TextInput labelText="Enter a stock to track" />
						</Hidden>
					</Column>
				</Grid>
			</Modal>
		</Row>
	</Grid>
</Content>
