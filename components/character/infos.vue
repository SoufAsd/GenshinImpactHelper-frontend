<template>
    <div>
        <div class="w-full text-gray-900 text-xl font-medium mb-2 text-white rounded text-sm"
            :style="{ background: dataCharacter.color }">{{ title }}</div>
        <div class="flex justify-center">
            <div class="flex flex-col md:flex-row md:max-w-xl">
                <img class=" w-full h-96 object-cover md:w-48 rounded-t-lg md:rounded-none md:rounded-l-lg"
                    :src="dataCharacter.img" alt="" />
                <div class="p-6 flex flex-col justify-start">
                    <section class="character-name-section">
                        <h3 class="text-gray-900 text-x font-medium mb-2 text-white rounded text-sm"
                            :style="{ background: dataCharacter.color }">name</h3>
                        <p class="text-gray-700 font-bold capitalize text-2xl mb-4" :style="{ color: dataCharacter.color }">
                            {{ dataCharacter.name }}
                        </p>
                    </section>
                    <section class="character-description-section">
                        <h3 class="text-gray-900 text-x font-medium mb-2 text-white rounded text-sm"
                            :style="{ background: dataCharacter.color }">description</h3>
                        <p class="text-gray-700 font-medium text-sm mb-4" :style="{ color: dataCharacter.color }">
                            {{ dataCharacter.description }}
                        </p>
                    </section>
                </div>
            </div>
        </div>
    </div>
    <!-- <div class="flex justify-center">
        <div class="flex flex-col">
            <div class="h-48 lg:h-auto lg:w-48 flex-none bg-cover bg-no-repeat rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden"
                :style="{backgroundImage: 'url(' + dataCharacter.img + ')'}" title="image-avatar">
            </div>
            <div class="rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal">
                <div class="mb-8">
                    <p class="text-sm text-gray-600 flex items-center">
                        <svg class="fill-current text-gray-500 w-3 h-3 mr-2" xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 20 20">
                            <path
                                d="M4 8V6a6 6 0 1 1 12 0v2h1a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2v-8c0-1.1.9-2 2-2h1zm5 6.73V17h2v-2.27a2 2 0 1 0-2 0zM7 6v2h6V6a3 3 0 0 0-6 0z" />
                        </svg>
                        Members only
                    </p>
                    <div class="text-gray-900 font-bold text-xl mb-2">Best Mountain Trails 2020</div>
                    <p class="text-gray-700 text-base">Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                        Voluptatibus quia, Nonea! Maiores et perferendis eaque, exercitationem praesentium nihil.</p>
                </div>
                <div class="flex items-center">
                    <div class="text-sm">
                        <p class="text-gray-900 leading-none">John Smith</p>
                        <p class="text-gray-600">Aug 18</p>
                    </div>
                </div>
            </div>
        </div>
    </div> -->
</template>
<script>
export default {
    props: {
        title: {
            type: String
        },
        dataCharacter: {
            type: Object
        }
    },
    data() {
        return {

        }
    },
    created() {
        console.log(this.dataCharacter.color)
    }
}
</script>