<template>
    <p>
       Lingua: <span class="fi" :class="ln"></span>
    </p>
</template>

<script>
export default {
    name: "flagComponent",
    data(){
        return{
            ln: 'fi-'+ this.getflag(this.languages),
            // languageCorrect: 
        }
    },
    props: {
        languages: String
    },
    methods:{
        getflag(string){
            
            switch (string) {
                case 'en': {
                    string = 'gb';
                    break;
                }
                case 'ja': {
                    string = 'jp';
                    break;
                }
                case 'ko': {
                    string = 'kr';
                    break;
                }
                case 'zh': {
                    string = 'cn';
                    break;
                }
                case 'da': {
                    string = 'dk';
                    break;
                }
            }
            return string;
        }
    }
}
</script>

<style lang="scss" scoped>


</style>