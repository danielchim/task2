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

	} from "carbon-components-svelte";

	let isSideNavOpen = false;
</script>

<Header company="Stonks" bind:isSideNavOpen>
	<svelte:fragment slot="skip-to-content">
		<SkipToContent />
	</svelte:fragment>
</Header>

<SideNav bind:isOpen={isSideNavOpen}>
	<SideNavItems>
		<SideNavLink text="Home" href="/"/>
		<SideNavDivider />
		<TextInput style="margin:5%" placeholder="Enter stock name..." />

		<SideNavLink text="TSLA" href="/stock"/>
		<SideNavLink text="GME" />
		<SideNavLink text="YOLO" />
	</SideNavItems>
</SideNav>

<Content>
	<main>
		<slot />
	</main>
</Content>
