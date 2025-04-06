<script lang="ts">
    import { ShoppingBasket } from 'lucide-svelte'
    import { HandPlatter } from 'lucide-svelte'
    import { Calendar } from 'lucide-svelte'
    import { Cloud } from 'lucide-svelte'
    import { CloudDrizzle } from 'lucide-svelte'
    import { Sun } from 'lucide-svelte'

    let name = 'Scuttle'
    let img = '/Profile_-_Scuttle.png'

    let orderNum = 42;
    let ShiftStart = "16:00";
    let shiftEnd = "20:00";

    let nextShiftDay1 = "Wed, 17"
    let nextShiftTime1 = "17:00-23:00"
    let nextShiftDay2 = "Fri, 17"
    let nextShiftTime2 = "12:00-17:00"

    let weatherWeek = [
        ["13:00", Cloud],
        ["14:00", Sun],
        ["15:00", Sun],
        ["16:00", Cloud],
        ["17:00", CloudDrizzle], 
        ["18:00", CloudDrizzle]]
    let temp = "15°C"

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
        <div class="bg-white h-40 flex w-[352px] lg:w-[416px] rounded-3xl">
            {#each weatherWeek as day}
                <div class="bg-[#DADADA] rounded-2xl justify-around items-center flex flex-1 flex-col m-1">
                    <p>{day[0]}</p> 
                </div>
            {/each}
        </div>
        <div class="bg-white h-40 flex w-[352px] lg:w-[416px] rounded-3xl ">
            <div class="w-1/2 flex flex-col font-inter m-8 items-start justify-center">
                <p class="">Today's Shift</p>
                <p class="font-semi-bold text-3xl">{ShiftStart}</p>
                <p class="font-semi-bold text-3xl">{shiftEnd}</p>
            </div>
            <div class="w-3/4 flex flex-col font-inter mr-2">
                <p class="m-1.5 text-sm text-right self-end">Next Shifts</p>
                <div class="flex flex-col justify-between h-3/4">
                    <div class="bg-[#DADADA] h-14 rounded-xl flex flex-row justify-around items-center text-sm">
                        <p class="font-semi-bold">{nextShiftDay1}</p>
                        <p class="text-[#878787]">{nextShiftTime1}</p>
                    </div>
                    <div class="bg-[#DADADA] h-14 rounded-xl flex flex-row justify-around items-center text-sm">
                        <p class="font-semi-bold">{nextShiftDay2}</p>
                        <p class="text-[#878787]">{nextShiftTime2}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</main>

<style lang="postcss">
    :global(html) {
        background-color: theme(colors.gray.100);
    }
</style>