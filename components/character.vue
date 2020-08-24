<template>

    <div class="card">
        <div class="card-content">
            <h4 class="link" v-if="!single"><b><nuxt-link :to="`characters/${id}`"> {{data.name}} </nuxt-link></b></h4>
            <h4 v-else>
            <b> {{data.name}} </b>
            <p> Eye Color - {{data.eye_color}} </p>
            <p> Birth Year - {{data.birth_year}} </p>
            <p> Gender - {{data.gender}} </p>
            <p> Skin Color - {{data.skin_color}} </p>

            &nbsp;
            <p class="exit"><nuxt-link to='/'><b>Go Back</b></nuxt-link></p>
            </h4>
            <!-- <p> {{data.height}} </p> -->
        </div>
    </div>

</template>

<script>
export default {
    props: {
        data: {
            type: Object,
            default() {
                return {}
            } 
        },
        id: {
            type: Number,
            default: 0
        },
        single: {
            type: Boolean,
            default: false
        }
    }
}
</script>

<style scoped>
    * {
        font-family: 'comfortaa', 'Open sans';
    }

    .card {
        box-shadow: 0.4px 4px 0 rgba(0, 0, 0, 0.2);
        transition: 0.3s;
        margin: 15px auto;
        width: 50%;
    }

    .card:hover {
        box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
    }

    .card-content {
        margin: 20px 0;
        padding: 10px 16px;
    }

    .exit {
        color: #ff0000;
        font-size: 14px;
    }

    .link {
        color: #ff0000;
    }
</style>