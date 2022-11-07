<template>
    <CharacterForm :actualCharacter="mycharacter"></CharacterForm>
</template>
<script>
export default {
    layout: 'navbar',
    data: () => ({
        mycharacter: Array
    }),
    mounted() {
        
    },
    async fetch() {
        this.mycharacter = await fetch(
            'http://localhost:4000/character/' + this.$route.params.name
        ).then(res => res.json())
        // var image = await fetch(
        //     'https://api.genshin.dev/characters/' + this.$route.params.name + '/gacha-splash'
        // ).then(res => {
        //     return res.url
        // })

        // this.mycharacter = [{"image":image}]
        
        // return await this.mycharacter
    },
}
</script>