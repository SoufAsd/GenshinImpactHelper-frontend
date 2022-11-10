<template>
    <div>
        <div id="modal-container">
            <div class="modal-background">
                <div class="modal">
                    <h2>{{ this.modaltype }}</h2>
                    <svg class="modal-svg" xmlns="http://www.w3.org/2000/svg" width="100%" height="100%"
                        preserveAspectRatio="none">
                        <rect x="0" y="0" fill="none" width="100%" height="100%" rx="3" ry="3"></rect>
                    </svg>
                </div>
            </div>
        </div>
        <Nuxt />
    </div>
</template>
<!--  -->
<style>
#modal-container {
    display: table;
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
    transform: scale(0);
    z-index: 1;
}

#modal-container.open {
    transform: scale(1);
}

#modal-container.open .modal-background {
    background: rgba(0, 0, 0, 0);
    animation: fade 0.5s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
}

#modal-container.open .modal-background .modal {
    background-color: transparent;
    animation: modalFadeIn 0.5s 0.8s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
}

#modal-container.open .modal-background .modal h2,
#modal-container.open .modal-background .modal p {
    opacity: 0;
    position: relative;
    animation: modalContentFadeIn 0.5s 1s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
}

#modal-container.open .modal-background .modal .modal-svg rect {
    animation: sketchIn 0.5s 0.3s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
}

#modal-container.open.out {
    animation: quickScaleDown 0s 0.5s linear forwards;
}

#modal-container.open.out .modal-background {
    animation: fadeOut 0.5s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
}

#modal-container.open.out .modal-background .modal {
    animation: modalFadeOut 0.5s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
}

#modal-container.open.out .modal-background .modal h2,
#modal-container.open.out .modal-background .modal p {
    animation: modalContentFadeOut 0.5s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
}

#modal-container.open.out .modal-background .modal .modal-svg rect {
    animation: sketchOut 0.5s cubic-bezier(0.165, 0.84, 0.44, 1) forwards;
}

#modal-container .modal-background {
    display: table-cell;
    background: rgba(0, 0, 0, 0.8);
    text-align: center;
    vertical-align: middle;
}

#modal-container .modal-background .modal {
    background: white;
    padding: 50px;
    border-radius: 3px;
    font-weight: 300;
    position: relative;
}

#modal-container .modal-background .modal h2 {
    font-size: 25px;
    line-height: 25px;
    margin-bottom: 15px;
}

#modal-container .modal-background .modal p {
    font-size: 18px;
    line-height: 22px;
}

#modal-container .modal-background .modal .modal-svg {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    border-radius: 3px;
}

#modal-container .modal-background .modal .modal-svg rect {
    stroke: #fff;
    stroke-width: 2px;
    stroke-dasharray: 778;
    stroke-dashoffset: 778;
}

@keyframes fade {
    0% {
        background: rgba(219, 219, 219, 0);
    }

    100% {
        background: rgba(219, 219, 219, 0);
    }
}

@keyframes fadeOut {
    0% {
        background: rgba(0, 0, 0, 0.7);
    }

    100% {
        background: rgba(0, 0, 0, 0);
    }
}

@keyframes modalFadeIn {
    0% {
        background-color: transparent;
    }

    100% {
        background-color: white;
    }
}

@keyframes modalFadeOut {
    0% {
        background-color: white;
    }

    100% {
        background-color: transparent;
    }
}

@keyframes sketchIn {
    0% {
        stroke-dashoffset: 778;
    }

    100% {
        stroke-dashoffset: 0;
    }
}

@keyframes modalContentFadeIn {
    0% {
        opacity: 0;
        top: -20px;
    }

    100% {
        opacity: 1;
        top: 0;
    }
}

@keyframes quickScaleDown {
    0% {
        transform: scale(1);
    }

    99.9% {
        transform: scale(1);
    }

    100% {
        transform: scale(0);
    }
}

@keyframes modalContentFadeOut {
    0% {
        opacity: 1;
        top: 0px;
    }

    100% {
        opacity: 0;
        top: -20px;
    }
}

@keyframes sketchOut {
    0% {
        stroke-dashoffset: 0;
    }

    100% {
        stroke-dashoffset: 778;
    }
}
</style>


<script>
export default {
    props: {
        modaltype: String
    },
    watch: {
        modaltype(oldVal, newVal) {
            // console.log(this.modaltype)
        }
    }
}
</script>
