<template>
    <ion-page>
        <ion-header :translucent="true">
            <ion-toolbar>
                <ion-title>{{ test }}</ion-title>
            </ion-toolbar>
        </ion-header>

        <ion-content :fullscreen="true">
            <ion-header collapse="condense">
                <ion-toolbar>
                    <ion-title size="large">{{ test }}</ion-title>
                </ion-toolbar>
            </ion-header>

            <div id="container">
                <strong>Ready to create an app?</strong>
                <p>
                    Start with Ionic
                    <a
                        target="_blank"
                        rel="noopener noreferrer"
                        href="https://ionicframework.com/docs/components"
                        >UI Components</a
                    >
                </p>
                <ion-slides>
                    <ion-slide>
                        <h1>Slide 1</h1>
                    </ion-slide>
                    <ion-slide>
                        <h1>Slide 2</h1>
                    </ion-slide>
                    <ion-slide>
                        <h1>Slide 3</h1>
                    </ion-slide>
                </ion-slides>
            </div>
        </ion-content>
    </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonSlides } from "@ionic/vue";
import axios from "axios";
import { defineComponent } from "vue";

export default defineComponent({
    name: "HomePage",
    components: {
        IonContent,
        IonHeader,
        IonSlides,
    },
    data() {
        return {
            test: "awikwok",
        };
    },
    setup() {
        axios
            .get("http://127.0.0.1:5000/result/ahaha@gmail.com")
            .then((res) => {
                console.log(res);
            })
            .catch((err) => {
                console.log(err);
            });
    },
});
</script>

<style scoped>
#container {
    text-align: center;

    position: absolute;
    left: 0;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
}

#container strong {
    font-size: 20px;
    line-height: 26px;
}

#container p {
    font-size: 16px;
    line-height: 22px;

    color: #8c8c8c;

    margin: 0;
}

#container a {
    text-decoration: none;
}
</style>
