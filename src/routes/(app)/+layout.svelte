<script>
    import Navbar from "$lib/Navbar.svelte";
    import Sidebar from "$lib/Sidebar.svelte";

    let hasSidebar = false;
    
    let toggleSidebar;
    let navbarFixed = true;

    function onMenuClick(){
        toggleSidebar();
    }
</script>

<body>
{#if hasSidebar}
    <Navbar navbarFixed={navbarFixed} hasSidebar on:click={onMenuClick}/>
    <Sidebar bind:toggleSidebar={toggleSidebar}/>
{:else}
    <Navbar navbarFixed={navbarFixed}/>    
{/if}

    <slot/>
    <br style="margin-bottom: 3rem;">
    <div class="footer"><h1>Placeholder</h1></div>
</body>

<style>
    body{
        min-width: 100%;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        margin: 0;
        padding: 0;
    }

    .footer{
        position: relative;
        margin: 0%;
        /* margin-top: 10px; */
        margin-top: auto;
        margin-bottom: 0px;
        padding-bottom:0px;
        bottom: 0px;
        width: 100%;
        height: 16rem;
        background-color: black;
        opacity: 80%;
        display: flex;
        justify-content: center;
        align-items: center;
        color: white;
    }
</style>
