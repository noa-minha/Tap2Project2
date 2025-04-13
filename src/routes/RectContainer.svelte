<script>
    export let bgColor = "bg-white";   
    export let gap = "gap-4";
    export let extra ="";
</script>
  
<div class={`${bgColor} ${gap} ${extra} h-40 flex w-[352px] lg:w-[416px] rounded-3xl`}>
    <slot />
</div>
