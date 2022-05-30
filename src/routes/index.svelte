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
		ClickableTile,
	} from "carbon-components-svelte";
	import "carbon-components-svelte/css/white.css";
	import Hidden from "../lib/modal/Hidden.svelte";
	let open = false;
	let show;
	let shown;
</script>

<Content>
	<Grid fullWidth padding noGutter>
			<Column>
				<h1>All stocks</h1>
			</Column>
			<Column
				id="myelement"
			>
			<Button size="small" on:click={() => (open = true)}
				>New stock</Button
			>
			</Column>
			<Modal
				bind:open
				modalHeading="New stock"
				primaryButtonText="Add"
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
							<TextInput
								labelText="Include words"
								helperText="Use commas to seperate them"
							/>
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
						<Column>
							<DatePicker datePickerType="single" style="margin-bottom:1rem">
								<DatePickerInput
									labelText="Starting date"
									placeholder="mm/dd/yyyy"
								/>
							</DatePicker>
							<TimePicker
								labelText="Starting time"
								placeholder="hh:mm"
							>
								<TimePickerSelect value="pm">
									<SelectItem value="am" text="AM" />
									<SelectItem value="pm" text="PM" />
								</TimePickerSelect>
							</TimePicker>
						</Column>

						<Column>
							<DatePicker datePickerType="single" style="margin-bottom:1rem">
								<DatePickerInput
									labelText="Ending date"
									placeholder="mm/dd/yyyy"
								/>
							</DatePicker>
							<TimePicker
								labelText="End time"
								placeholder="hh:mm"
							>
								<TimePickerSelect value="pm">
									<SelectItem value="am" text="AM" />
									<SelectItem value="pm" text="PM" />
								</TimePickerSelect>
							</TimePicker>
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
		<Column noGutter>
			<ClickableTile href="/stock">
				<Grid noGutter>
					<Column
						style="display: flex; flex-direction:row; justify-content:space-between; margin:0%"
						noGutter
					>
						<h2>TSLA</h2>
					</Column>
				</Grid>
			</ClickableTile>
		</Column>
		<Column noGutter>
			<ClickableTile href="/stock">
				<Grid noGutter>
					<Column
						style="display: flex; flex-direction:row; justify-content:space-between; margin:0%"
						noGutter
					>
						<h2>TSLA</h2>
					</Column>
				</Grid>
			</ClickableTile>
		</Column>
	</Grid>
</Content>
