<template>
    <div class="container">
        <div v-if="read">
            <qrcode-stream @decode="onDecode"></qrcode-stream>
            <qrcode-drop-zone></qrcode-drop-zone>
            <qrcode-capture></qrcode-capture>
        </div>
        <div class="btn btn-primary btn-sm" @click=" read = ! read ">{{ read === true ? 'close' : 'open' }}</div>
    </div>
</template>

<script>

    import { QrcodeStream, QrcodeDropZone, QrcodeCapture } from 'vue-qrcode-reader'

    export default {
//        components: {
//            QrcodeStream,
//            QrcodeDropZone,
//            QrcodeCapture
//        },
        data(){
          return {
              read: true,
          }
        },
        mounted() {
            console.log('Component mounted.')
        },
        methods: {
            onDecode (decodedString) {
                console.log(decodedString)
            }
        },

    }
</script>
