<template>
    <div>
        <h1>La page consacrée à : {{land.post_title}}</h1>
        <img :src="land.flag"/>
        <ul>
            <li>ID: {{land.ID}}</li>
        </ul>
    </div>
</template>

<script>
import axios from "axios";
export default {
    data(){
        return{
            land:[]
        }
    },
    mounted(){
        let nbr = this.$route.params.land;
        axios.get("http://www.ddivoux.mmi.o2switch.site/wp-json/wp/v2/monstre").then(response => this.land = response.data[nbr]);
    }
}
</script>