<template>
    <div class="modal" :class="modalstyle" @click="shutModal()">
        <div>
            <div class="modal-container" @click="stopDefault">
                <div class="modal-head"  v-show="title">{{title}}</div>
                <slot name="body"></slot>
                <div class="modal-foot">
                    <slot name="confirm"></slot>
                    <button class="btn-default" type="button" @click="cancers()"><slot name="cancer">取消</slot></button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        data(){
            return{
            }
        },

        methods:{
            shutModal(){
                this.modalstyle.show = false;
            },
            cancers(){
                this.modalstyle.show = false;
            },
            confirm(){
                this.modalstyle.show = false;
            },
            stopDefault(event){
              event.stopPropagation();
            }
        },

        props:{
            modalstyle:{
                required:true,
                type:Object,
            },
            title:{
                required:false,
                type:String,
            }
        }
    }
</script>