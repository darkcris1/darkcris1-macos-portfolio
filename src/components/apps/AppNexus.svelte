<script lang="ts">
  import type { AppID } from '__/stores/apps.store';

  export let appID: AppID;
  export let isBeingDragged: boolean;
</script>

{#if appID === 'calendar'}
  {#await import('./Calendar/Calendar.svelte') then { default: Calendar }}
    <Calendar />
  {/await}
{:else if appID === 'vscode'}
  {#await import('./VSCode/VSCode.svelte') then { default: VSCode }}
    <VSCode {isBeingDragged} />
  {/await}
{:else if appID === 'portfolio'}
  {#await import('./Portfolio/Portfolio.svelte') then { default: Portfolio }}
    <Portfolio {isBeingDragged} />
  {/await}
{:else if appID === 'mail'}
  {#await import('./Email/Email.svelte') then { default: Email }}
    <Email {isBeingDragged} />
  {/await}
{:else if appID === 'calculator'}
  {#await import('./Calculator/Calculator.svelte') then { default: Calculator }}
    <Calculator />
  {/await}
{:else}
  {#await import('./Placeholder/Placeholder.svelte') then { default: Placeholder }}
    <Placeholder {appID} />
  {/await}
{/if}
