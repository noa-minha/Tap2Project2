<script lang="ts">
	let name = 'Scuttle';
    let img = '/Profile_-_Scuttle.png'
</script>

<header class="mt-10 mb-12 flex flex-col items-center justify-center text-center">
    <img class="m-5 rounded-full w-28 h-28 object-top" src={img} alt="Your profile pic" />
    <h1 class="font-inter font-semi-bold text-3xl object-bottom">Good Morning {name}!</h1>
</header>


<div class="flex flex-col items-center justify-center text-center">
    hey hey grid stuff
</div>

<style lang="postcss">
:global(html) {
    background-color: theme(colors.gray.100);
}
</style>