<script>
    import ChristmasAnimation from "$lib/ChristmasAnimation.svelte";
    import Button from "$lib/Button.svelte";
    import ChristmasCountdown from "$lib/ChristmasCountdown.svelte";
    import XmasTree from "$lib/XmasTree.svelte";
    import { onMount } from "svelte";
    import { goto } from "$app/navigation";

    onMount(() => {
        if (window.innerWidth <= 768) {
            goto("/mobile");
        }
    });

    function comingSoon() {
        alert("Coming very soon!");
    }

    function goToDays() {
        goto("/submit");
    }

    function faq(){
      goto("/faq");
    }
</script>

<ChristmasCountdown />
<ChristmasAnimation />
<XmasTree />

<div class="button-container">
	<Button on:click={goToDays}>Submit</Button>
	<Button on:click={comingSoon}>Shop</Button>
	<Button on:click={faq}>FAQ</Button>
	<Button href="/auth/logout">Log Out</Button>
</div>

<style>
  .button-container {
    position: fixed;
    bottom: 2rem;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    gap: 1rem;
    z-index: 200;
  }

  @media (max-width: 768px) {
    .button-container {
      bottom: 1rem;
      gap: 0.5rem;
      flex-wrap: wrap;
      justify-content: center;
      padding: 0 1rem;
      max-width: 100%;
    }
  }

  @media (max-width: 480px) {
    .button-container {
      bottom: 0.75rem;
      gap: 0.4rem;
    }
  }
</style>
