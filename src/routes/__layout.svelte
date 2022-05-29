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
		<TextInput placeholder="Enter user name..." />
		<SideNavLink text="Link 1" href="/stock"/>
		<SideNavLink text="Link 2" />
		<SideNavLink text="Link 3" />
	</SideNavItems>
</SideNav>

<Content>
	<main>
		<slot />
	</main>
</Content>
