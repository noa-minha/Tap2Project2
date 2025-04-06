<script lang="ts">
	let name = 'Scuttle';
    let img = '/Profile_-_Scuttle.png'

    import { ShoppingBasket } from 'lucide-svelte';
    import { HandPlatter } from 'lucide-svelte';
    import { Calendar } from 'lucide-svelte';

    let orderNum = 42;
    let ShiftStart = "16:00";
    let shiftEnd = "20:00";

    let items = ['Hello', 'Banana', 'Ciao']

</script>

<header class="mt-10 mb-12 flex flex-col items-center justify-center text-center">
    <img class="m-5 rounded-full w-24 h-24 object-top" src={img} alt="Your profile pic" />
    <h1 class="font-inter font-semi-bold text-3xl object-bottom">Good Morning {name}!</h1>
</header>

<main class="flex flex-col gap-y-4">
    <div class="flex lg:flex-row flex-col lg:gap-x-4 gap-y-4 items-center justify-center mx-auto">
        <div class="h-40 gap-4 flex">
            <button class="w-[170px] lg:w-[200px] bg-[#0358F1] rounded-3xl flex flex-col items-start justify-end p-4 gap-2 hover:opacity-75 transition-opacity duration-50">
                <ShoppingBasket class="text-white"/>
                <p class="font-inter text-xl text-white">Checkout</p>
            </button>

            <button class="w-[170px] lg:w-[200px] bg-black rounded-3xl flex flex-col items-start justify-end p-4 gap-2 hover:opacity-75 transition-opacity duration-50">
                <HandPlatter class="text-white"/>
                <p class="font-inter text-xl text-white">Orders</p>
            </button>
        </div>

        <div class="h-40 gap-4 flex">
            <button class="w-[170px] lg:w-[200px] bg-black rounded-3xl flex flex-col items-start justify-end p-4 gap-2 hover:opacity-75 transition-opacity duration-50">
                <Calendar class="text-white" />
                <p class="font-inter text-xl text-white">Scheduler</p>
            </button>

            <div class="w-[170px] lg:w-[200px] bg-white rounded-3xl font-inter flex flex-col items-center justify-center text-center">
                <p>orders today</p>
                <p class="font-semi-bold text-3xl">{orderNum}</p>
            </div>
        </div>
    </div>

    <div class="flex lg:flex-row flex-col lg:gap-x-4 gap-y-4 justify-center mx-auto">
        <div class="bg-red-800 h-40 flex w-[352px] lg:w-[416px] rounded-3xl">
        </div>
        <div class="bg-white h-40 flex w-[352px] lg:w-[416px] rounded-3xl ">
            <div class="w-1/2 flex flex-col font-inter m-8 items-start justify-center">
                <p class="">Today's Shift</p>
                <p class="font-semi-bold text-3xl">{ShiftStart}</p>
                <p class="font-semi-bold text-3xl">{shiftEnd}</p>
            </div>
            <div class="w-1/2 flex flex-col font-inter mr-2">
                <p class="m-0.5">Next Shifts</p>
                <div class="flex flex-col justify-between h-3/4">
                    <div class="bg-[#DADADA] h-14 rounded-xl">

                    </div>
                    <div class="bg-[#DADADA] h-14 rounded-xl">
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="flex flex-col items-center justify-center text-center">
        {#each items as item}
            <p>{item}</p>
        {/each}
    </div>
</main>

<style lang="postcss">
    :global(html) {
        background-color: theme(colors.gray.100);
    }
</style>