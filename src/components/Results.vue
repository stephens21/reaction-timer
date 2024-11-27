<script>
export default {
    name:'Result-vue',
    props:['score'],
    components:{},
    data(){
        return {
            rank:null
        }

    },
    mounted(){
        if(this.score < 250){
            this.rank = 'Ninja Fingers'
        }else if (this.score < 400){
            this.rank = 'Rapid Reflexees'
        }else{
            this.rank = 'Snail pace...'
        }

    },
    methods:{

    }
    
}
</script>

<template>
    <p>Reaction time - {{ score }} ms</p>
    <p class="rank">{{ rank }}</p>
</template>
<style>
.rank{
    color: #0faf87;
    font-size: 1.4em;
    font-weight: bold;
}

</style>