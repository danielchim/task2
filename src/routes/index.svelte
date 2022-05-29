<script>
	import {
		Content,
		Grid,
		Row,
		Column,
		Button,
		Modal,
		TextInput,
		MultiSelect,
		Toggle,
		DatePicker,
		DatePickerInput,
		TimePicker,
		TimePickerSelect,
		SelectItem,
		Checkbox,
		Search,
		Tile,
	} from "carbon-components-svelte";
	import "carbon-components-svelte/css/white.css";
	import Card from "../lib/components/card.svelte";
	import Hidden from "../lib/modal/Hidden.svelte";
	let open = false;
	let show;
	let shown;
</script>

<Content>
	<Grid fullWidth padding noGutter>
		<Row>
			<Column
				style="display: flex; flex-direction:row; justify-content:space-between"
			>
				<h1>All stocks</h1>
				<Button on:click={() => (open = true)}>New stock</Button>
			</Column>
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
						<Search placeholder="Enter a stock to track" />
					</Column>
					<Column>
						<Button on:click={show}>Advanced options</Button>
					</Column>
					<Hidden bind:shown bind:show>
						<h4>Advanced options</h4>
						<Column noGutter>
							<MultiSelect
								style="margin-bottom: 5%; "
								titleText="Source"
								label="Select data source..."
								items={[
									{ id: "0", text: "Reddit" },
									{ id: "1", text: "Weibo" },
									{ id: "2", text: "Twitter" },
								]}
							/>
						</Column>
						<Column noGutter>
							<TextInput labelText="Include words" helperText="Use commas to seperate them"/>
						</Column>
						<Column noGutter>
							<TextInput labelText="Exclude words" />
						</Column>
						<Column noGutter>
							<TextInput labelText="User Mentions" />
						</Column>
						<Column noGutter>
							<TextInput labelText="Hashtags" />
						</Column>
						<Column noGutter>
							<MultiSelect
								titleText="Language"
								label="Select language..."
								items={[
									{ id: "0", text: "Chinese (Tradtional)" },
									{ id: "1", text: "English" },
									{ id: "2", text: "Japanese" },
								]}
							/>
						</Column>
						<Column noGutter>
							<Toggle labelText="Include replies" />
						</Column>
						<Column noGutter>
							<Toggle labelText="Include retweets" />
						</Column>
						<Column noGutter>
							<TextInput
								labelText="Reactions"
								placeholder="Minimum likes:"
							/>
						</Column>
						<Column noGutter>
							<TextInput placeholder="Minimum replies:" />
						</Column>
						<Column noGutter>
							<DatePicker datePickerType="range" on:change>
								<DatePickerInput
									labelText="Start date"
									placeholder="mm/dd/yyyy"
								/>
								<DatePickerInput
									labelText="End date"
									placeholder="mm/dd/yyyy"
								/>
							</DatePicker>
						</Column>

						<Column noGutter>
							<TextInput
								labelText="How many posts you want to retreive? (First 100 posts are for free!)"
								placeholder="No. of posts:"
							/>
						</Column>
						<Column noGutter>
							<Checkbox
								labelText="I agreee to pay $0.00 to retreive 100 posts"
							/>
						</Column>
					</Hidden>
				</Grid>
			</Modal>
		</Row>
		<Column noGutter>
			<Tile on:click={() => (window.location = "/stock")}>
				<h2>TSLA</h2>
				<Button>Primary button</Button>
			</Tile>
		</Column>
	</Grid>
</Content>
