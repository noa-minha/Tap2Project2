<script lang="ts">
    import { ShoppingBasket, HandPlatter, Calendar, Cloud, CloudDrizzle, Sun} from 'lucide-svelte'

    import SquareTile from './SquareTile.svelte';

    /* since some of the data is not just fixated text but changing data that comes from a differenc source
    I tried to mimic it by using variables for the non-static data*/

    let name = 'Scuttle'
    /* I left the picture in static because in order to access it from lib because it would 
     involve setting up a tool to deal with static assets - I wanted to focus on tailwind and not get into that */
    let img = '/Profile_-_Scuttle.png'

    let orderNum = 42;
    let ShiftStart = "16:00";
    let shiftEnd = "20:00";

    let nextShiftDay1 = "Wed, 17"
    let nextShiftTime1 = "17:00-23:00"
    let nextShiftDay2 = "Fri, 17"
    let nextShiftTime2 = "12:00-17:00"

    let weather = [
    { time: "13:00", icon: Cloud },
    { time: "14:00", icon: Sun },
    { time: "15:00", icon: Sun },
    { time: "16:00", icon: Cloud },
    { time: "17:00", icon: CloudDrizzle },
    { time: "18:00", icon: CloudDrizzle }
];
    let temp = "15°C"

</script>

<header class="mt-10 mb-12 flex flex-col items-center justify-center text-center">
    <img class="m-5 rounded-full w-24 h-24 object-top" src={img} alt="Your profile pic" />
    <h1 class="font-inter font-semi-bold text-3xl object-bottom">Good Morning {name}!</h1>
</header>

<main class="flex flex-col gap-y-4">

    <!-- top 4 buttons -->
    <div class="flex lg:flex-row flex-col lg:gap-x-4 gap-y-4 items-center justify-center mx-auto">
        <div class="h-40 gap-4 flex">
            <SquareTile bgColor="bg-[#0358F1]">
                <ShoppingBasket class="text-white"/>
                <p class="font-inter text-xl text-white">Checkout</p>
            </SquareTile>

            <SquareTile>
                <HandPlatter class="text-white"/>
                <p class="font-inter text-xl text-white">Orders</p>
            </SquareTile>
        </div>

        <div class="h-40 gap-4 flex">
            <SquareTile>
                <Calendar class="text-white" />
                <p class="font-inter text-xl text-white">Scheduler</p>
            </SquareTile>

            <SquareTile isButton={false} bgColor="bg-white">
                <p>orders today</p>
                <p class="font-semi-bold text-3xl">{orderNum}</p>
            </SquareTile>
        </div>
    </div>

    <!-- bottom shift and weather info panels -->
    <div class="flex lg:flex-row flex-col lg:gap-x-4 gap-y-4 justify-center mx-auto">
        <div class="bg-white h-40 flex w-[352px] lg:w-[416px] rounded-3xl p-1 font-inter font-semi-bold text-sm justify-around">
            {#each weather as {time, icon}, i}
                <div class="rounded-2xl items-center flex flex-1 flex-col m-1 pt-1 pb-1" 
                class:bg-[#DADADA]={i === 0}
                class:bg-white={i !== 0}>
                    <p class="justify-start" class:text-[#DADADA]={i !== 0}>{time}</p> 
                    <section class="flex flex-grow flex-col justify-end">
                    {#if icon}
                    <svelte:component this={icon} class="w-6 h-6" />
                    {/if} 
                    <p>{temp}</p>   
                    </section>            
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

<!-- 
I'm leaving this one in since even if I take the highest div in the project and color the bg
using tailwind it still does not color the whole bg -->

<style lang="postcss">
    :global(html) {
        background-color: theme(colors.gray.100);
    }
</style>