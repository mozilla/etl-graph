<script>
    import { Nav, NavItem, NavLink } from "sveltestrap/src";
    export let segment;
    let items = [
        { href: "/", name: "home" },
        { href: "notes", name: "notes" },
    ];
</script>

<Nav class="ml-auto" tabs>
    {#each items as item}
        <NavItem>
            <NavLink
                active={item.href == '/' ? !segment : item.name == segment}
                href={item.href}>
                {item.name}
            </NavLink>
        </NavItem>
    {/each}
</Nav>
