<template>
    <div id="background" class="flex justify-center h-screen w-full">
        <backgroundCharacter />
        <div class="flex flex-col md:flex-row md:max-w-xl rounded-lg shadow-md" style="max-width: 47rem;max-height: 47rem;">
            <CharacterForm :actualCharacter="mycharacter" :type="key"></CharacterForm>
            <!-- <CharacterInformations></CharacterInformations> -->
        </div>
    </div>
</template>
<script>
export default {
    layout: 'sidebar',
    props:["nuxtChildKey"],
    data: () => ({
        mycharacter: Array,
        key : ""
    }),
    // created(){
    //     console.log(this.nuxtChildKey)
    //     console.log(this.$el)
    // },
    mounted(){
        this.key = this.nuxtChildKey
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