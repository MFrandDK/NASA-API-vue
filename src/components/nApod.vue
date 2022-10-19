<template>
<article>
    
    <div class="imageWrapper" v-if="nasaData.media_type == 'image'">
        <a :href="nasaData.hdurl" target="_blank">

            <img :src="nasaData.url" :alt="nasaData.title" />

        </a>
        <div class="imageText">
            <h2>{{ nasaData.title }}</h2>
            <div>
                <p>{{nasaData.explanation}}</p>
                <h6>{{ displayCopyright() }}</h6>
            </div>
        </div>
    </div>

    <div class="imageWrapper" v-else>
        <a :href="nasaData.url" target="_blank" class="videoLink">

            <img :src="nasaData.url"/>

        </a>
        
    </div>
</article>

</template>

<script>


export default {
    name: 'nApod',
    data() {
        return {
            nasaData: ''
        };
    },
    props: ['date'],
    created() {
        return fetch(
            'https://api.nasa.gov/planetary/apod?api_key=Ot4l5yvwK4E688azgJrDhttp46o2stPxLvfCfCQL'
        )
            .then(data => data.json())
            .then(data => (this.nasaData = data));
    },
    methods: {
        displayCopyright() {
            if (this.nasaData.copyright) {
                return `Copyright © ${this.nasaData.copyright}`;
            } else {
                return '';
            }
        }
    },
    watch: {
        date: {
            immediate: true,
            deep: true,
            handler() {
                return fetch(
                    `https://api.nasa.gov/planetary/apod?date=${this.date}&api_key=Ot4l5yvwK4E688azgJrDhttp46o2stPxLvfCfCQL`
                )
                    .then(data => data.json())
                    .then(data => (this.nasaData = data));
            }
        }
    }
};
</script>

<style scoped>

article {
	max-width: 100%;
}

img {
    max-width: 100%;
}

.imageWrapper {
	position: relative;
    margin-top: 2rem;
}
h2 {
    margin: 1rem 0;
}
.imageText {
	opacity: 0;
	width: 80%;
	position: absolute;
	top: 50%;
	left: 50%;
    color: white;
    text-align: left;
	transform: translate(-50%, -50%);
	background-color: rgba(0,0,0,.5);
	padding: 2%;
	transition: all .3s ease-in-out;
}

.imageWrapper:hover .imageText {
	opacity: 1;
}
.videoLink {
	display: block;
}
</style>
