<script>
    export let person;

    import { getContext } from "svelte";
    import PersonProfile from "./personProfile.svelte";

    const { open } = getContext("simple-modal");
    const showModal = () => open(PersonProfile, { person: person });
</script>

<div class="picwrapper">
    <img
        src={person.picture.thumbnail}
        alt="The rock"
        class="profilePic"
        on:click={showModal}
        on:keypress={showModal}
    />
</div>

<div class="namewrapper">
    <h1 on:click={showModal} on:keypress={showModal}>
        {person.name.first}
        {person.name.last}
    </h1>
</div>

<style>
    .profilePic {
        max-width: 3.5rem;
        max-height: 3.5rem;
        border-radius: 50%;
    }

    .namewrapper {
        display: flex;
        flex: 1.5;
        align-self: center;
    }

    .picwrapper {
        flex: 1;
    }

    h1 {
        font-size: 20px;
        line-height: 24px;
        font-weight: 400;
    }
</style>
