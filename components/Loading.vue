

<template>
    <div class="flex items-center content-center">
        <UModal :ui="{
            container:'flex min-h-full items-center justify-center ',
            background: 'bg-transparent dark:bg-transparent',
            base: '',
            shadow:'',
            fullscreen: 'w-screen h-screen',
        }" v-model="value" prevent-close>
            <img class=""  src="https://document.jmtnetwork.co.th/logo/loading_Asset0.gif" style="width: 80%;height: auto; margin-left:10%"/>
        </UModal>
    </div>
</template>

<style>
#slidecaption {
    -webkit-animation-name: spinner;
    -webkit-animation-timing-function: linear;
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-duration: 1s;
    animation-name: spinner;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
    animation-duration: 1s;
    -webkit-transform-style: preserve-3d;
    -moz-transform-style: preserve-3d;
    -ms-transform-style: preserve-3d;
    transform-style: preserve-3d;
}

/* WebKit and Opera browsers */
@-webkit-keyframes spinner {
    from {
        -webkit-transform: rotateY(0deg);
    }

    to {
        -webkit-transform: rotateY(-360deg);
    }
}

/* all other browsers */
@keyframes spinner {
    from {
        -moz-transform: rotateY(0deg);
        -ms-transform: rotateY(0deg);
        transform: rotateY(0deg);
    }

    to {
        -moz-transform: rotateY(-360deg);
        -ms-transform: rotateY(-360deg);
        transform: rotateY(-360deg);

    }
}
</style>

<script setup>
import { computed } from 'vue'

const props = defineProps(['modelValue'])
const emit = defineEmits(['update:modelValue'])

const value = computed({
    get() {
        return props.modelValue
    },
    set(value) {
        emit('update:modelValue', value)
    }
})
</script>

<style> .spinner_b2T7 {
     animation: spinner_xe7Q .8s linear infinite
 }

 .spinner_YRVV {
     animation-delay: -.65s
 }

 .spinner_c9oY {
     animation-delay: -.5s
 }

 @keyframes spinner_xe7Q {

     93.75%,
     100% {
         r: 3px
     }

     46.875% {
         r: .2px
     }
 }
</style>