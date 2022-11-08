<template>
    <div class="flex justify-center">
        <div class="flex flex-col md:flex-row md:max-w-xl rounded-lg shadow-md" style="max-width: 47rem;max-height: 47rem;">
            <CharacterForm :actualCharacter="mycharacter"></CharacterForm>
            <!-- <CharacterInformations></CharacterInformations> -->
        </div>
    </div>
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
        if (location.hostname === "localhost" || location.hostname === "127.0.0.1") {
            var url = 'http://localhost:4000/character/' + this.$route.params.name;
        }else{
            var url = 'https://genshin-api-2idd.onrender.com/character/' + this.$route.params.name;
        }

        this.mycharacter = await fetch(
            url
        ).then(res => res.json())
    },
}
</script>