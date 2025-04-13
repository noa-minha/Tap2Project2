<script>
    export let isButton = true;          
    export let bgColor = "bg-black";      
    export let width = "w-[170px] lg:w-[200px]";
  </script>
  
  {#if isButton}
    <button class={`${width} ${bgColor} rounded-3xl flex flex-col items-start justify-end p-4 gap-2 hover:opacity-75 transition-opacity duration-50`}>
      <slot />
    </button>
  {:else}
    <div class={`${width} ${bgColor} rounded-3xl flex flex-col items-center justify-center text-center p-4`}>
      <slot />
    </div>
  {/if}