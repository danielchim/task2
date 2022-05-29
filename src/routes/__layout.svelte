<script>
	import {
		Header,
		SideNav,
		SideNavItems,
		SideNavLink,
		SideNavDivider,
		SkipToContent,
		Content,
		TextInput,
		Grid,
		Row,
		Column,
	} from "carbon-components-svelte";
	let isSideNavOpen = false;
</script>

<Header company="Stonks" bind:isSideNavOpen>
	<svelte:fragment slot="skip-to-content">
		<SkipToContent />
	</svelte:fragment>
</Header>

<SideNav bind:isOpen={isSideNavOpen} expansionBreakpoint="1684">
	<SideNavItems>
		<SideNavLink text="Home" href="/" />
		<SideNavDivider />
		<TextInput style="margin:5%" placeholder="Enter stock name..." />

		<SideNavLink text="TSLA" href="/stock" />
		<SideNavLink text="GME" />
		<SideNavLink text="YOLO" />
	</SideNavItems>
</SideNav>
<Content>
	<Grid noGutter>
		<Row noGutter>
			<Column noGutter>
				<main>
					<slot />
				</main>
			</Column>
		</Row>
	</Grid>
</Content>
