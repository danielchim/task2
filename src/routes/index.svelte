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
			<Column>
				<h1>All stocks</h1>
			</Column>
			<Column>
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
						<TextInput labelText="Enter a stock to track" />
					</Column>
					<Column>
						<Button on:click={show}>Advanced options</Button>
					</Column>
					<Hidden bind:shown bind:show>
						<h4>Advanced options</h4>
						<MultiSelect
							titleText="Source"
							label="Select contact methods..."
							items={[
								{ id: "0", text: "Slack" },
								{ id: "1", text: "Email" },
								{ id: "2", text: "Fax" },
							]}
						/>
						<TextInput labelText="Include words" />
						<TextInput labelText="Exclude words" />
						<TextInput labelText="Mentions" />
						<TextInput labelText="Hashtags" />
						<MultiSelect
							titleText="Contact"
							label="Select contact methods..."
							items={[
								{ id: "0", text: "Slack" },
								{ id: "1", text: "Email" },
								{ id: "2", text: "Fax" },
							]}
						/>
						<Toggle labelText="Push notifications" />
						<Toggle labelText="Push notifications" />
						<TextInput
							labelText="Reactions"
							placeholder="Minium likes:"
						/>
						<TextInput
							labelText="Reactions"
							placeholder="Minium likes:"
						/>
						<Grid fullWidth>
							<Row>
								<Column>
									<DatePicker
										datePickerType="single"
										on:change
									>
										<DatePickerInput
											labelText="Time range"
											placeholder="mm/dd/yyyy"
										/>
									</DatePicker>
									<TimePicker placeholder="hh:mm">
										<TimePickerSelect value="pm">
											<SelectItem value="am" text="AM" />
											<SelectItem value="pm" text="PM" />
										</TimePickerSelect>
										<TimePickerSelect value="pdt">
											<SelectItem
												value="pdt"
												text="PDT"
											/>
											<SelectItem
												value="gmt"
												text="GMT"
											/>
										</TimePickerSelect>
									</TimePicker>
								</Column>
								<Column noGutter
									><DatePicker
										datePickerType="single"
										on:change
									>
										<DatePickerInput
											labelText="Time range"
											placeholder="mm/dd/yyyy"
										/>
									</DatePicker>
									<TimePicker placeholder="hh:mm">
										<TimePickerSelect value="pm">
											<SelectItem value="am" text="AM" />
											<SelectItem value="pm" text="PM" />
										</TimePickerSelect>
										<TimePickerSelect value="pdt">
											<SelectItem
												value="pdt"
												text="PDT"
											/>
											<SelectItem
												value="gmt"
												text="GMT"
											/>
										</TimePickerSelect>
									</TimePicker></Column
								>
							</Row>
						</Grid>
						<TextInput
							labelText="How many posts you want to retreive?"
							placeholder="No. of posts:"
						/>
						<Checkbox
							labelText="I agreee to pay $0.00 to retreive 100 posts"
						/>
					</Hidden>
				</Grid>
			</Modal>
		</Row>
		<Column>
			<Card
				borderBottom
				title="Carbon Charts Svelte"
				subtitle="20+ charts, powered by d3"
				href="/stock"
			/>
		</Column>
	</Grid>
</Content>
