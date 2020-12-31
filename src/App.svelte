<script>
    import Header from './components/Header.svelte';
    import Footer from './components/Footer.svelte';
    import Tabs from './shared/Tabs.svelte';
    import PollForm from './components/PollForm.svelte';
    import PollList from './components/PollList.svelte';

    // tabs
    let tabsItems = [
        { name: 'Poll List', active: true },
        { name: 'Add New Poll', active: false },
    ];

    const tabChange = (e) => {
        Object.keys(tabsItems).forEach( function (key) {
            tabsItems[key].active = tabsItems[key].name === e.detail
        });
    }

    // store
    let polls = [];

    const handleAdd = (e) => {
        const poll = e.detail;
        polls = [poll, ...polls];
        tabChange({detail: 'Poll List'});
    }

</script>

<Header />
<main>
    <Tabs {tabsItems} on:tabChange={tabChange} />
    {#each tabsItems as item}
        {#if item.active && item.name === "Poll List"} 
            <PollList polls = {polls} />
        {:else if item.active && item.name === "Add New Poll"}
            <PollForm on:add = {handleAdd}/>
        {/if}
    {/each}
</main>
<Footer />

<style>
    main {
        max-width: 960px;
        margin: 40px auto;
    }
</style>