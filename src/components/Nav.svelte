<script>
    import { Nav, NavItem, NavLink } from "sveltestrap/src";
    export let segment;
    let items = [{ href: "/", name: "home" }];
</script>

<Nav class="ml-auto" tabs>
    {#each items as item}
        <NavItem>
            <NavLink active={items.name == segment} href={item.href}>
                {item.name}
            </NavLink>
        </NavItem>
    {/each}
</Nav>
