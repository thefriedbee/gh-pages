<script>
    import {createEventDispatcher} from "svelte";
    const dispatch = createEventDispatcher();

    export let items;
    export let activeItem;

    export let languages;
    export let activeLang;
</script>

<header>
    <nav class="d-flex flex-wrap py-3 mb-4 border-bottom navbar navbar-default fixed-top bg-light">
        <div class="container-fluid headertitle">
            <!-- <svg class="bi me-2" width="100" height="40"><use xlink:href="#bootstrap"/></svg> -->
            <!-- <a href="#" class="d-flex align-items-center mb-3 mb-md-0 me-md-auto text-dark text-decoration-none"></a> -->
            <div class="d-flex justify-content-start">
                <span class="fs-4 mybrand">Diyi Liu's website</span>
                <!-- <button>
                    <span class="fs-4">Diyi Liu's website</span>
                </button> -->

                <ul class="nav nav-pills">
                    {#each languages as lang}
                        <li class="nav-item" on:click={() => dispatch('langChange', lang)}>
                            <span class="nav-link langbt" class:active={lang === activeLang}
                            aria-current="page">{lang}</span>
                        </li>
                    {/each}
                </ul>
            </div>

            <!-- <div class="d-flex justify-content-start">
                <button>
                    <span class="fs-4">Diyi Liu's website</span>
                </button>
            </div> -->
            
            
            <ul class="nav nav-pills justify-content-end">
                {#each items as item}
                    <li class="nav-item" on:click={() => dispatch('tabChange', item)}>
                        <a href="#{item}" class="nav-link" class:active={item === activeItem}
                        aria-current="page">{item}</a>
                    </li>
                {/each}
            </ul>
        </div>
    </nav>
</header>

<style>
    .headertitle {
        margin: auto 15%;
    }
    .mybrand {
        margin: 0 30px;
    }
</style>