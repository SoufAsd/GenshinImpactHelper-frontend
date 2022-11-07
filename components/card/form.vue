<template>
    <div class="card">
        <img class="avatar" :src="character.img" alt="" sizes="" srcset="">
        <div class="infos"><div class="name">{{character.name}}</div></div>
    </div>
</template>
<script>
export default {
    props: {
        character : []
    },
}
</script>