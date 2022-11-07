<template>
    <div class="feed-in grid grid-cols-5 gap-4 place-items-center pt-6 m-auto">
        <div v-for="character of characters">
            <NuxtLink :to="`/character/${character.name}`">
                <CardForm :character="character" />
            </NuxtLink>
        </div>
    </div>
</template>

<script>
export default {
    layout: 'navbar',
    data: () => ({
        characters: []
    }),
    async fetch() {
        this.characters = await fetch(
            'http://localhost:4000/character'
        ).then(res => res.json())
        // var allcharacters = await fetch(
        //     'https://api.genshin.dev/characters'
        // ).then(res => res.json())

        // allcharacters.map(async (item, i) => {
        //     if (!item.includes("traveler")) {
        //         var image = await fetch(
        //             'https://api.genshin.dev/characters/' + item + '/icon-big'
        //         ).then(res => {
        //             return res.url
        //         }).catch(err => err)
        //         if (image) {
        //             this.characters.push({ "name": item, "img": image })
        //         }
        //     }
        // })
    },
}
</script>