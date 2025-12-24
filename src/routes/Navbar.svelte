<!-- NavBar shown at the top of all pages -->
<script>
  import { base, slack, github } from '$lib/constants';
  import NavbarBase from '$lib/Navbar/NavbarBase.svelte';
  import NavList from '$lib/Navbar/NavList.svelte';
  import NavListItem from '$lib/Navbar/NavListItem.svelte';
</script>

<NavbarBase>
  <NavList>
    <NavListItem href={base || '/'} big>MIA Lab</NavListItem>
  </NavList>
  <NavList>
    <NavListItem href="{base}/topics">Topics</NavListItem>
    <NavListItem href="{base}/getting-started">Getting Started</NavListItem>
    <NavListItem href="{base}/exercises">Exercises</NavListItem>
    <NavListItem href={slack} external>GitBook</NavListItem>
    <NavListItem href={github} external>GitHub</NavListItem>
  </NavList>
</NavbarBase>
